DIVER Overview
==============

The DIVER application consists of four distinct parts:

* `diverweb`, a React.JS-based web application, statically built from Javascript/SASS/HTML assets using the create-react-app suite and stored in the `diverweb` repository.
* `diverRPC`, a middleware API server that provides the data for diverweb, implemented as a Flask-based Python WSGI app and stored in the `diverRPC` repository.
* `db_procs`, SQL stored procedures that diverRPC uses for interacting with the DIVER database; implemented in SQL generated via PyExpander macro code and also stored in the `diverRPC` repository.
* The DIVER database, versioned by number (and which is dependent on a 'built' database called `DIVER_ref` that is version-dated); the build and management tools and scripting are in a private repository maintained by MathMed.

For integration with a larger site (such as incorporating said site's site-wide menus), one should modify `public/index.html` in the `diverweb` repository as needed.


Suggested Steps For Deploying DIVER
===================================

You will need:

* Database dumps `DIVER` and `DIVER_ref_2025011917`
* Access to `https://github.com/MathematicalMedicine/DIVER` and subrepos (or a fork of same)


Part 1: Base Environment Setup
------------------------------

1. Start with a RHEL-based Linux system, as that's what these instructions assume.
2. Create a `/var/lib/diver` directory for the application. The contents of the DIVER repo should be copied (or cloned) to this directory (so that you end up with `/var/lib/diver/diverRPC`, `/var/lib/diver/diverweb`, and `/var/lib/diver/diver-codebooks`).
3. Create a `/var/lib/diver/www-root` directory.
5. Create the following symlink:
    * `/var/lib/diver/diver-codebooks/dist` -> `/var/lib/diver/www-root/codebooks`


Part 2: Build and Runtime Environments
--------------------------------------

1. Download [Miniforge for Linux](https://github.com/conda-forge/miniforge); install it to `/var/lib/diver/miniforge/`. Skip the "add to your bash profile" step when asked during install, as it is unnecessary.
2. Temporarily add `/var/lib/diver/miniforge/bin/` to your PATH; this is to ensure that the next step takes place in the miniforge environment.
3. Install the following packages into the Miniforge environment, via `conda` if possible or `pip` if not:
    * `gunicorn`
    * `flask=2.2.5` (version 2.2.5 required; later versions will not work)
    * `pyexpander`
    * `pytest` (OPTIONAL for part 4 step 4)
    * `pymysql`
    * `jsonschema`
    * `flask-cors`
    * `crowd` (will likely require pip)
    * `flask-pymysql` (will likely require pip)
4. Download and install Node.js version 20.


Part 3: System Environment
--------------------------

### 3.1 - MySQL

1. In MySQL 8, create two databases for DIVER that you will be restoring provided database dumps to. One should be named `DIVER` and the other `DIVER_ref_2025011917`.
2. Add a MySQL user that has full privileges for both databases.
3. Load database dumps into the two databases, starting with `DIVER_ref_2025011917` first.

### 3.2 - diverRPC

1. In `/var/lib/diver/diverRPC/`, create a `diver.cnf` file (based off of `diver.cnf.template`) and add to it the user credentials you created in Part 3.1 step 1, as well as the URL and credentials for the Atlassian Crowd instance you will be authenticating against.
2. Configure SELinux policies to allow diverRPC to run and interoperate with the rest of the system. This can vary based on your system(s) and your chosen policies.
    * In our testing, we found that the following policies needed to be added: 

        allow init_t var_lib_t:file execute;
        allow init_t var_lib_t:file execute_no_trans;
        allow init_t mysqld_port_t:tcp_socket name_connect;
    * We also found that three booleans each had to be set to 1 using `setsebool -P`: `httpd_can_network_connect`, `domain_can_mmap_files`, and `nis_enabled`
    * These were necessary for a configuration in which the MySQL and Apache servers were on the same system as diverRPC; results may vary.
    * If your policy differs from the default or if you chose to install in a different location, you may have to do your own experimentation and investigation with `audit2allow` and the like to get the correct policies in.
3. Copy `/var/lib/diver/diverRPC/diverRPC.service` to `/etc/systemd/system/`.
4. Enable the diverRPC systemd service added in part 3 step 6 with `systemctl daemon-reload; systemctl enable diverRPC`

### 3.3 - Apache

1. Modify your nginx or apache2 configuration to do the following:
    * Serve at root all static assets from `/var/lib/diver/www-root/` (and follow symlinks from that directory as well)
    * Proxy all requests starting with `/api/` to `http://127.0.0.1:8000/api/`
    * Direct all other requests to root's `index.html`.
    * It is also strongly recommended to set up a TLS certificate; doing so is beyond the scope of this guide.
    * We have a sample Apache virtualhost configuration that can be shared as needed (it's not included here as it assumes, among other things, use of Let's Encrypt for TLS).


Part 4: Building and Deploying
------------------------------

1. Temporarily add `/var/lib/diver/miniforge/bin/` to your PATH if you haven't already; this is to ensure that the next step takes place in the miniforge environment.
2. In `/var/lib/diver/diverRPC/`, execute the following command: `PYTHONPATH="." expander.py -af diverRPC-procs.sql.pyexp>diverRPC-procs.sql` (This generates the actual SQL code for DIVER's stored procedures from macro files).
3. Run the mysql client and connect to your `DIVER` database, then `SOURCE diverRPC-procs.sql`. (This loads the DIVER stored procedures into the database.)
    * Important Note: It may be necessary to repeat the command a second time if errors are encountered on the first attempt with a no-existing-procs dump, as there are some interdependencies in the definitions of some user-defined functions therein.
4. OPTIONAL: In `/var/lib/diver/diverRPC/`, run `pytest` to verify diverRPC is working correctly.
5. In `/var/lib/diver/diverweb/`, run `npm install` and wait for the environment setup to complete. IMPORTANT: Ignore any "vulnerabilities" reported, as they do not affect the running website ([reference/explanation here](https://github.com/facebook/create-react-app/issues/11174)).
6. Run `npm run build`. (This generates diverweb's static HTML/CSS files and a static Javascript bundle in the `build/` subdirectory.)
7. Copy all the contents of `/var/lib/diver/diverweb/build/` to `/var/lib/diver/www-root/`
8. Start or restart the `mysqld`, `httpd`, and `diverRPC` services.
