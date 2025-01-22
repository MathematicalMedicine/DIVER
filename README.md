# DIVER

Tracking integrated versioned components for the NRGR DIVER application, currently in prerelease.

All actual development takes place in the repos for those components, rather than in this repo; this is just how we keep track of what component versions come together for the final package. (We don't even track that final package version here; that's in diverweb's `.env` file). We do, however, do issue tracking here.

Component repos are currently restricted-access. Whether or not that changes is still being reviewed.

# ChangeLog

Prior to 1.0.0-prerelease.1, the below version tracking information was being maintained in a "Just Deployed On DIVER" shared document, as part of testing between NRGR collaborators.


## 1.0.0-prerelease.3
(diverweb 0.50.1, diverRPC 0.33.2, db\_procs 0.30.2, db\_edit 75)

* Partial revert and extension of fix for [#286](https://github.com/MathematicalMedicine/DIVER/issues/286); datestamp comparisons had been inadvertently broken in the process.


## 1.0.0-prerelease.2 (data update redeployment)
(diverweb 0.50.1, diverRPC 0.33.2, db\_procs 0.30.1, db\_edit 75)

* Found and corrected a number of instances in which the "observations" field for many variables was incorrectly given as 0.
* Pulled "flag variables" (previously misleadingly known as "dichotomous variables") from the data distribution due to information correctness concerns.


## 1.0.0-prerelease.2
(diverweb 0.50.1, diverRPC 0.33.2, db\_procs 0.30.1, db\_edit 74)

* Fixed an issue in which greater/less than and greater/less than or equal to comparisons could get incorrect results ([#286](https://github.com/MathematicalMedicine/DIVER/issues/286)).
* Fixed multiple issues in which MySQL 8 compatibility work introduced bugs, particularly with custom variables ([#291](https://github.com/MathematicalMedicine/DIVER/issues/291), [#293](https://github.com/MathematicalMedicine/DIVER/issues/293)).
* Download Data now properly allows you to re-preview if you change the cohort and/or variable set being downloaded ([#294](https://github.com/MathematicalMedicine/DIVER/issues/294)).


## 1.0.0-prerelease.1
(diverweb 0.50.0, diverRPC 0.33.1, db\_procs 0.30.0, db\_edit 74)

* Implemented application-wide versioning scheme in preparation for public release as part of the NRGR site.
* Dichotomous variables are barred from use in Downcode-style Custom Variables (owing to having no useful effect).
* A few minor display bugs fixed.
* "Fair Use" notice added for codebooks
* NRGR website menus template updated.
* MySQL 8 now supported by diverRPC backend ([#246](https://github.com/MathematicalMedicine/DIVER/issues/246)).
* Fixed a bug that prevented use of "distribution" variables in Custom Variables or in downloads.


## 2024-11-29 17:31:32-0500
(diverweb 0.49.3, diverRPC 0.32.4, db\_procs 0.28.5, db\_edit 73)

* Happy Thanksgiving!
* The Download Data page now informs users if their intended download requires collections they don't have access to, and does a better job of handling users without any data access ([#280](https://github.com/MathematicalMedicine/DIVER/issues/280), [#282](https://github.com/MathematicalMedicine/DIVER/issues/282)).


## 2024-11-27 17:25:04-0500
(diverweb 0.49.2, diverRPC 0.32.3, db\_procs 0.28.4, db\_edit 73)

* There are now two buttons for DIVER help - one takes you to the ToC ("How To Use DIVER") and one takes you to context-sensitive help ("Help For This Page") ([#276](https://github.com/MathematicalMedicine/DIVER/issues/276)).
* Preview Download now shows all records, paginated ([#279](https://github.com/MathematicalMedicine/DIVER/issues/279)).
* Fixed a bug in which the NRGR website navigation menus would appear partially obscured.


## 2024-11-05 10:45:18-0500
(diverweb 0.49.1, diverRPC 0.32.2, db\_procs 0.28.4, db\_edit 73)

* Corrected a pair of oversights in the procs that were supposed to be part of the prior update but were somehow overlooked.


## 2024-11-05 09:40:05-0500
(diverweb 0.49.1, diverRPC 0.32.2, db\_procs 0.28.3, db\_edit 73)

* Dichotomous variables should now be functioning properly ([#262](https://github.com/MathematicalMedicine/DIVER/issues/262)).
* Fixed an issue that could cause the first attempt of some operations to fail and subsequent attempts go through just fine ([#273](https://github.com/MathematicalMedicine/DIVER/issues/273)).


## 2024-11-01 00:09:28-0400
(diverweb 0.49.0, diverRPC 0.32.1, db\_procs 0.28.2, db\_edit 73)

* Many variable information display bugs fixed ([#68](https://github.com/MathematicalMedicine/DIVER/issues/68)).


## 2024-10-31 12:26:35-0400
(diverweb 0.48.1, diverRPC 0.32.1, db\_procs 0.28.1, db\_edit 73)

* DIVER Help documentation updated to reflect changes to the Ascertain Pedigrees module ([#268](https://github.com/MathematicalMedicine/DIVER/issues/268)).


## 2024-10-28 12:41:20-0400
(diverweb 0.48.1, diverRPC 0.32.1, db\_procs 0.28.1, db\_edit 72)

* Many data fixes to variables that were proving to be unusable in many parts of DIVER due to harmonization issues ([#248](https://github.com/MathematicalMedicine/DIVER/issues/248)).
* Small clarifying text change in variable selection ([#269](https://github.com/MathematicalMedicine/DIVER/issues/269)).


## 2024-10-25 17:08:27-0400
(diverweb 0.48.0, diverRPC 0.32.1, db\_procs 0.28.1, db\_edit 71)

* Several changes to the Ascertain Pedigrees module to better fit intended workflow and fix bugs ([#261](https://github.com/MathematicalMedicine/DIVER/issues/261), [#236](https://github.com/MathematicalMedicine/DIVER/issues/236), [#266](https://github.com/MathematicalMedicine/DIVER/issues/266)).


## 2024-10-21 12:48:28-0400
(diverweb 0.47.4, diverRPC 0.31.1, db\_procs 0.27.5, db\_edit 71)

* Pedigree cohort summary info now includes counts of individuals ([#223](https://github.com/MathematicalMedicine/DIVER/issues/223)).
* Delete dialogs are now consistent between all item types (and inform the user they can sometimes take a while) ([#258](https://github.com/MathematicalMedicine/DIVER/issues/258)).


## 2024-10-18 20:57:09-0400
(diverweb 0.47.3, diverRPC 0.31.1, db\_procs 0.27.4, db\_edit 71)

* 'BETWEEN' constraints should now work properly ([#58](https://github.com/MathematicalMedicine/DIVER/issues/58)).
* Fixed an error in which variable names were being limited to an unusually short length - and a large number of other internal considerations that sprang from same ([#256](https://github.com/MathematicalMedicine/DIVER/issues/256)).
* Preemptively addressed an issue in which Crowd users with long usernames (longer than 32 characters) would have experienced inexplicable repeated failures trying to use DIVER ([#257](https://github.com/MathematicalMedicine/DIVER/issues/257)).
* Fixed an error in which variable downcoding using 'BETWEEN' would not work properly ([#104](https://github.com/MathematicalMedicine/DIVER/issues/104); was actually part of prior update but only later discovered it addressed this issue as well).


## 2024-10-08 12:50:03-0400
(diverweb 0.47.3, diverRPC 0.31.0, db\_procs 0.27.1, db\_edit 70)

* Major update to the database; many more variables' data types are now properly designated ([#253](https://github.com/MathematicalMedicine/DIVER/issues/253)).
* Combine Two Variables and Ascertain Pedigrees will now *only* allow categorical variables to be used - this restriction was already in place, but was inconsistently enforced ([#225](https://github.com/MathematicalMedicine/DIVER/issues/225)).
* Fixed an error in which the first character of a variable set name could not ever be deleted ([#233](https://github.com/MathematicalMedicine/DIVER/issues/233)).
* Removed a few things that weren't working as planned, in prep for release candidate ([#251](https://github.com/MathematicalMedicine/DIVER/issues/251), [#254](https://github.com/MathematicalMedicine/DIVER/issues/254)).
* Fixed multiple Variable Details display bugs.


## 2024-09-17 16:13:13-0400
(diverweb 0.47.1, diverRPC 0.31.0, db\_procs 0.27.1, db\_edit 66)

* Fixed a bug that, under some circumstances, could prevent a download from being previewable or downloadable. ([#252](https://github.com/MathematicalMedicine/DIVER/issues/252))


## 2024-08-28 15:41:25-0400
(diverweb 0.47.1, diverRPC 0.31.0, db\_procs 0.26.0, db\_edit 66)

* Data Download now has a "preview" function (which is required before download occurs). ([#98](https://github.com/MathematicalMedicine/DIVER/issues/98), [#239](https://github.com/MathematicalMedicine/DIVER/issues/239))
* Fixed a bug in which one could accidentally double-click a submit button ([#247](https://github.com/MathematicalMedicine/DIVER/issues/247))
* Fixed a bug in Combine Two Variables that would prevent saving. ([#250](https://github.com/MathematicalMedicine/DIVER/issues/250))
* The DIVER documentation has now been updated to reflect the changes to data download workflow, along with information on our harmonization process ([#218](https://github.com/MathematicalMedicine/DIVER/issues/218), [#243](https://github.com/MathematicalMedicine/DIVER/issues/243)), and on types of variables one can expect to find in DIVER.


## 2024-06-20 11:12:02-0400
(diverweb 0.46.2, diverRPC 0.29.1, db\_procs 0.25.5, db\_edit 65)

* The "DIVER Help" link is now context-sensitive and will now take you to appropriate sections of the DIVER documentation depending on where you are in the application when you click on it. ([#221](https://github.com/MathematicalMedicine/DIVER/issues/221))
* Removed extraneous confusing "delete" buttons from the Download page. ([#234](https://github.com/MathematicalMedicine/DIVER/issues/234))


## 2024-06-12 14:44:29-0400
(diverweb 0.46.1, diverRPC 0.29.1, db\_procs 0.25.5, db\_edit 65)

* Application is now NRGR site integration ready. NRGR's login form (found by clicking on "Log in" at the top of the page) should now be used.
* Data admins now have access to all data like they should, as opposed to none. ([#238](https://github.com/MathematicalMedicine/DIVER/issues/238))
* Fixed a bug that made "does not contain (value)" constraint types in creating custom variables and cohorts fail. ([#241](https://github.com/MathematicalMedicine/DIVER/issues/241))
* Supporting software platform updated. ([#51](https://github.com/MathematicalMedicine/DIVER/issues/51))
* "Search tags" have been updated to make some key variables easier to find.


## 2024-05-21 15:21:08-0400
(diverweb 0.44.3, diverRPC 0.28.3, db\_procs 0.25.3, db\_edit 62)

* The DIVER modules are now presented in a slightly different order to better fit expected workflow. No other changes have been made.


## 2024-05-20 14:03:44-0400
(diverweb 0.44.3, diverRPC 0.28.3, db\_procs 0.25.3, db\_edit 62)

* DIVER has been switched over to use the NRGR authentication and credentials system. Going forward one should access the site via [diver.nimhgenetics.org](https://diver.nimhgenetics.org). "diver.mathmed.org" will continue to work for the time being but is deprecated.


## 2024-05-15 19:34:10-0400
(diverweb 0.44.3, diverRPC 0.28.3, db\_procs 0.25.3, db\_edit 62)

* Fixed a bug that made previewing pedigree ascertainment unusually slow.


## 2024-05-15 17:29:23-0400
(diverweb 0.44.3, diverRPC 0.28.3, db\_procs 0.25.2, db\_edit 62)

* DIVER documentation updated and expanded. ([#222](https://github.com/MathematicalMedicine/DIVER/issues/222), [#227](https://github.com/MathematicalMedicine/DIVER/issues/227))


## 2024-05-14 17:47:40-0400
(diverweb 0.44.2, diverRPC 0.28.3, db\_procs 0.25.2, db\_edit 62)

* When comparing two or more variables on the View Variable Details page, changing the current "show counts for" cohort now correctly updates counts for all variables present. ([#219](https://github.com/MathematicalMedicine/DIVER/issues/219))
* Fixed a bug in pedigree ascertainment that reversed two of the parameters. ([#236](https://github.com/MathematicalMedicine/DIVER/issues/236))


## 2024-05-14 11:38:51-0400
(diverweb 0.44.1, diverRPC 0.28.2, db\_procs 0.25.1, db\_edit 62)

* Combine Two Variables now treats NULL values as equivalent to UNKNOWN; the net effect is that Combine Two is now a *union* of the two variables' individuals rather than an intersection. ([#213](https://github.com/MathematicalMedicine/DIVER/issues/213))
* The "Unknown" value is now pre-added as a value option for all custom variable creation. (It presently shows up as `[UNK]`).
* Fixed a bug in top_answers generation that caused searching for certain keywords to blank the entire webapp. ([#235](https://github.com/MathematicalMedicine/DIVER/issues/235))


## 2024-05-07 13:28:55-0400
(diverweb 0.44.0, diverRPC 0.28.1, db\_procs 0.25.0, db\_edit 61)

* Lots of behind-the-scenes stabilization and security work has taken place with custom variable creation, fixing several bugs. ([#65](https://github.com/MathematicalMedicine/DIVER/issues/65), [#81](https://github.com/MathematicalMedicine/DIVER/issues/81), [#85](https://github.com/MathematicalMedicine/DIVER/issues/85), [#184](https://github.com/MathematicalMedicine/DIVER/issues/184), [#230](https://github.com/MathematicalMedicine/DIVER/issues/230))
* Data input fields enhanced; DIVER now has mechanisms in place to make sure invalid names for things cannot be accidentally entered. ([#35](https://github.com/MathematicalMedicine/DIVER/issues/35), [#195](https://github.com/MathematicalMedicine/DIVER/issues/195))
* Multiple small changes to text in the UX for clarification purposes. ([#220](https://github.com/MathematicalMedicine/DIVER/issues/220), [#228](https://github.com/MathematicalMedicine/DIVER/issues/228))
* User access to individual-level data is now controlled. ([#59](https://github.com/MathematicalMedicine/DIVER/issues/59)) IMPORTANT NOTE: As part of this change, we will be doing a user authentication system migration in the near future; this is currently being coordinated with ISI.


## 2024-01-08 13:21:13-0500
(diverweb 0.42.13, diverRPC 0.26.7, db\_procs 0.24.7, db\_edit 59)

* A persistent bug that could come up when creating multiple custom variables has been fixed ([#152](https://github.com/MathematicalMedicine/DIVER/issues/152), [#217](https://github.com/MathematicalMedicine/DIVER/issues/217))
* Tags added to some variables for DIGS sections.
* A few incorrect PDF pages for some instrument variables have been fixed.


## 2024-01-06 15:41:15-0500
(diverweb 0.42.13, diverRPC 0.26.7, db\_procs 0.24.7, db\_edit 58)

* Fixed a bug when previewing ascertained pedigrees.
* The DIVER documentation (in its present form) is now complete and available.


## 2024-01-05 14:32:58-0500
(diverweb 0.42.13, diverRPC 0.26.7, db\_procs 0.24.6, db\_edit 58)

* A "Help" button has been added with a very early (incomplete) first draft of DIVER documentation  ([#86](https://github.com/MathematicalMedicine/DIVER/issues/86), [#140](https://github.com/MathematicalMedicine/DIVER/issues/140), [#141](https://github.com/MathematicalMedicine/DIVER/issues/141) (partial), [#209](https://github.com/MathematicalMedicine/DIVER/issues/209) (partial)).
* NRGR header and footer dummied out to avoid ambiguous overlap between DIVER functions and nonfunctional NRGR website functions.
* Fixed pagination issues for DIGS 3.0 Revised 7 ([#205](https://github.com/MathematicalMedicine/DIVER/issues/205)). 


## 2024-01-04 15:20:44-0500
(diverweb 0.42.12, diverRPC 0.26.7, db\_procs 0.24.6, db\_edit 57)

* Bugfixes to display of top answers for custom variables.


## 2024-01-02 12:53:07-0500
(diverweb 0.42.11, diverRPC 0.26.7, db\_procs 0.24.6, db\_edit 57)

* "Tags" added to variable search, to make some particularly relevant variables easier to find (and to allow for the addition of ontological data).
* Fixed an error that occurred when attempting to create a cohort based on a custom variable ([#202](https://github.com/MathematicalMedicine/DIVER/issues/202)).
* An error that occurred when attempting to download data has been resolved ([#124](https://github.com/MathematicalMedicine/DIVER/issues/124)).


## 2023-12-25 19:04:05-0500
(diverweb 0.42.11, diverRPC 0.26.6, db\_procs 0.24.5, db\_edit 56)

* Variable Catalog search is now the default when selecting variables (as opposed to picking a Custom Variable)
* Custom variables are more consistently referred to as such throughout the app.
* More answers are displayed in the Top Answers field, if available.
* Some helpful reminder text added to the Custom Variable creation pages noting that yes, you *can* add new values even after you've started to define them.


## 2023-12-23 22:28:14-0500
(diverweb 0.42.10, diverRPC 0.26.6, db\_procs 0.24.5, db\_edit 56)

* When viewing a variable's details, the option now exists to limit the response counts to those individuals in a given cohort. (NOTE: at this time this does not work when comparing variables.)
* Creating a new project will automatically switch you to using that project.
* A bug that occurred when deleting the current project has been fixed.
* A bug discovered in subset cohort creation summaries has been fixed.
* A bug which could cause creation of cohorts using a custom variable as the constraining variable to behave unexpectedly has been fixed.
* Multiple small issues with variables missing question text and old invalid metavariables have been resolved ([#189](https://github.com/MathematicalMedicine/DIVER/issues/189), [#190](https://github.com/MathematicalMedicine/DIVER/issues/190)).
* Lots of SCID-5 question and explicit context text ("the other 90%") added  ([#187](https://github.com/MathematicalMedicine/DIVER/issues/187)).


## 2023-12-20 14:58:42-0500
(diverweb 0.42.9, diverRPC 0.26.4, db\_procs 0.24.4, db\_edit 53)

* Pedigree cohorts now have their own preview/summary format showing pedigree information rather than individuals information.


## 2023-12-19 17:43:47-0500
(diverweb 0.42.8, diverRPC 0.26.3, db\_procs 0.24.3, db\_edit 53)

* "Greater than or equal to" and "Less than or equal to" constraints for variables have been added.


## 2023-12-19 14:16:40-0500
(diverweb 0.42.7, diverRPC 0.26.2, db\_procs 0.24.2, db\_edit 52)

* Polishing work done on the Variable Details view; contributing variable links fixed on custom variables, Top Answers now shows more than 3 possibilities where applicable.
* Loading indicators added to Ascertain Pedigrees (previously overlooked).
* A missing harmonization for the `ANHEDONIA` variable was fixed (plus other data fixes)


## 2023-12-18 14:05:36-0500
(diverweb 0.42.6, diverRPC 0.26.2, db\_procs 0.24.2, db\_edit 50)

* Saving and deleting cohorts, custom variables, and variable sets now have loading indicators that show on the buttons.


## 2023-12-18 12:17:45-0500
(diverweb 0.42.5, diverRPC 0.26.2, db\_procs 0.24.2, db\_edit 50)

* Due to an oversight, the fix to `DELUSIONS` variable harmonization ([#175](https://github.com/MathematicalMedicine/DIVER/issues/175)) had not yet actually been deployed on diver.mathmed.org. This is now done.
* Variable search no longer requires you to switch between "keyword search" and "variable name search"; both happen simultaneously.
* When picking a variable, switching between "pick a custom variable" and "search for an existing variable" has been changed from a drop-down to radio buttons, per user feedback.
* Previewing a cohort (as part of creating one) now has a loading indicator.


## 2023-12-12 14:44:28-0500
(diverweb 0.42.4, diverRPC 0.26.1, db\_procs 0.24.1, db\_edit 49)

* Fixed a bug in which variables that could be constrained via greater than/less than/etc. in construct variable and cohort creation had lost the option to do so.


## 2023-12-09 17:06:59-0500
(diverweb 0.42.4, diverRPC 0.26.1, db\_procs 0.24.0, db\_edit 49)

* Variable set names can now be reused in different projects ([#158](https://github.com/MathematicalMedicine/DIVER/issues/158))


## 2023-12-08 13:16:45-0500
(diverweb 0.42.4, diverRPC 0.26.1, db\_procs 0.24.0, db\_edit 48)

* Many small issues arriving from custom variable names having to be globally unique should now be fixed ([#185](https://github.com/MathematicalMedicine/DIVER/issues/185))
* Attempting to create a cohort that ends up with no individuals should no longer cause a crash (it will still show an error by design; said error should however be much more informative).


## 2023-11-08 18:28:43-0500
(diverweb 0.42.4, diverRPC 0.26.1, db\_procs 0.23.2, db\_edit 47)

* Several fixes made to PDF offset information in database where errors were showing up ([#171](https://github.com/MathematicalMedicine/DIVER/issues/171)).
* Several date formatting issues fixed ([#174](https://github.com/MathematicalMedicine/DIVER/issues/174)).
* Fix to `DELUSIONS` variable harmonization ([#175](https://github.com/MathematicalMedicine/DIVER/issues/175)).
* An initial implementation of copying custom variables (only works between users, button only appears on the somewhat-buried Custom Variable Construction Details page) has been made available.


## 2023-11-03 13:05:48-0400
(diverweb 0.42.3, diverRPC 0.26.0, db\_procs 0.23.1, db\_edit 44)

* Deleting a project now also deletes all child items (cohorts, custom variables, variable sets) within that project ([#164](https://github.com/MathematicalMedicine/DIVER/issues/164)).


## 2023-10-25 13:52:49-0400
(diverweb 0.42.3, diverRPC 0.26.0, db\_procs 0.23.0, db\_edit 44)

* Fixed a bug preventing changing cohort parent when creating a new subset cohort ([#153](https://github.com/MathematicalMedicine/DIVER/issues/153)).


## 2023-10-23 17:04:10-0400
(diverweb 0.42.2, diverRPC 0.26.0, db\_procs 0.23.0, db\_edit 44)

* Fixed a bug that was preventing deletion of custom variables.


## 2023-10-23 16:17:26-0400
(diverweb 0.42.1, diverRPC 0.26.0, db\_procs 0.23.0, db\_edit 44)

* Fixed bugs in which the sandbox project was being used when it was inappropriate to do so (including an example in which cohorts would always be created in the sandbox project)
* The backend logs are now more comprehensive, enabling enhanced future user support ([#119](https://github.com/MathematicalMedicine/DIVER/issues/119)).


## 2023-10-11 16:43:08-0400
(diverweb 0.42.1, diverRPC 0.25.0, db\_procs 0.23.0, db\_edit 44)

* SCID-5 added (in early draft form; further information to come).
* 'CAPS\_' variables have been retired in favor of 'NRGR\_' variables.
* Study BP 181 added.
* Variable sets can now be deleted from the list of all sets ([#181](https://github.com/MathematicalMedicine/DIVER/issues/181)).
* A few small bugfixes have been made to custom variable creation (mostly involving what project they're part of). Some issues may remain in this area and it is still being tested.


## 2023-10-09 15:39:08-0400
(diverweb 0.42.0, diverRPC 0.25.0, db\_procs 0.22.0, db\_edit 42)

Most of the changes in these versions are not yet user-visible, with some exceptions:

* Variable search speed should now be considerably improved.
* A project's details page now shows all items (constructs, variable sets, cohorts) within that project ([#167](https://github.com/MathematicalMedicine/DIVER/issues/167)).


## 2023-09-08 15:38:08-0400
(diverweb 0.41.0, diverRPC 0.24.0, db\_procs 0.21.1, db\_edit 37)

* Per-user authentication is now in DIVER. Existing projects, cohorts, variable sets, and constructs that were under the "test user" have been reassigned to those who we believe created those items; if one of your projects or its children are missing, please contact Jo ([jvc@mathmed.org](mailto:jvc@mathmed.org)).
* Current project is now tracked on the backend instead of client-side. ([#90](https://github.com/MathematicalMedicine/DIVER/issues/90), [#55](https://github.com/MathematicalMedicine/DIVER/issues/55), [#127](https://github.com/MathematicalMedicine/DIVER/issues/127), [#133](https://github.com/MathematicalMedicine/DIVER/issues/133)).
* Delete buttons are now available from the Custom Variables listing ([#147](https://github.com/MathematicalMedicine/DIVER/issues/147)).


## 2023-06-08 10:36:21-0400
(diverweb 0.39.1, diverRPC 0.22.1, db\_procs 0.20.1, db\_edit 34)

* Initial implementation of Ascertain Pedigrees ([#134](https://github.com/MathematicalMedicine/DIVER/issues/134), [#135](https://github.com/MathematicalMedicine/DIVER/issues/135), [#136](https://github.com/MathematicalMedicine/DIVER/issues/136), [#142](https://github.com/MathematicalMedicine/DIVER/issues/142)).
* Fixed a bug in Combine Two Variables UX ([#150](https://github.com/MathematicalMedicine/DIVER/issues/150)).


## 2023-05-07 12:38:32-0400
(diverweb 0.38.6, diverRPC 0.21.4, db\_procs 0.19.2, db\_edit 30)

* In places where one is required to pick a variable for an operation, one can now switch back and forth between picking from variable search results and picking from a list of one's custom variables. This is semi-experimental and hastily done but seems to work as expected (albeit sometimes the Custom Variables list ends up looking squished; this is a known issue).
* "exists" and "is valid" have been removed from variable constraint lists per request.
* IMPORTANT NOTE: Combine Two Variables' UX appears to have a number of issues that come up in many different edge cases, and so it should be considered to be broken and unreliable for the time being. (See also [Github issue #150](https://github.com/MathematicalMedicine/DIVER/issues/150).)


## 2023-05-03 12:02:52-0400
(diverweb 0.38.5, diverRPC 0.21.4, db\_procs 0.19.2, db\_edit 30)

* Display of a custom variable upon creation should now be fixed.
* Variable Sets now properly display any custom variables that are part of the set ([#148](https://github.com/MathematicalMedicine/DIVER/issues/129)).


## 2023-05-03 11:22:31-0400
(diverweb 0.38.4, diverRPC 0.21.3, db\_procs 0.19.1, db\_edit 30)

* The search optimization from db\_procs 0.19.0 led to some errors with construct variables; these have been fixed.
* The Custom Variable landing page should now correctly show custom variables for the current project.
* Some errors that showed up when creating a new variable set or a new construct should now be removed.


## 2023-05-02 12:16:38-0400
(diverweb 0.38.3, diverRPC 0.21.2, db\_procs 0.19.0, db\_edit 30)

* Variable Search has been partially optimized and should now be faster. (More optimization is needed, though.)


## 2023-04-10 16:16:42-0400
(diverweb 0.38.3, diverRPC 0.21.2, db\_procs 0.18.2, db\_edit 30)

* Tokenized Keyword Search for variable question text is now active ([#26](https://github.com/MathematicalMedicine/DIVER/issues/26))


## 2023-04-10 11:12:57-0400
(diverweb 0.38.3, diverRPC 0.21.2, db\_procs 0.18.1, db\_edit 30)

* The fix for [#133](https://github.com/MathematicalMedicine/DIVER/issues/133) had broken view of individual construct variables. This should now be working again.


## 2023-04-07 13:47:42-0400
(diverweb 0.38.2, diverRPC 0.21.1, db\_procs 0.18.0, db\_edit 30)

Note: Some previous versions were not initially deployed to d.m.o as they involved internal restructuring without user-visible changes.

* The Suggest Edits form on the View Variable page should now be functional ([#129](https://github.com/MathematicalMedicine/DIVER/issues/129), [#130](https://github.com/MathematicalMedicine/DIVER/issues/130), [#131](https://github.com/MathematicalMedicine/DIVER/issues/131))
* Variable Search has most cases of "variables that don't show up" fixed ([#132](https://github.com/MathematicalMedicine/DIVER/issues/129))
* Variable Search, in most cases, should properly show constructs only in the current project ([#133](https://github.com/MathematicalMedicine/DIVER/issues/133))
* View Variables should no longer crash as a result of search restrictions ([#138](https://github.com/MathematicalMedicine/DIVER/issues/138), although the workaround may cause issues with viewing construct variables outside of the "Favorites" project; work is ongoing).
* Variable Set descriptions should now actually be saved ([#125](https://github.com/MathematicalMedicine/DIVER/issues/125))


## 2023-03-22 17:04:37-0400
(diverweb 0.38.0, diverRPC 0.19.1, db\_procs 0.16.2, db\_edit 28)

* The View Variable page now has a form for submitting suggested edits to variable data, although it is presently nonfunctional ([#122](https://github.com/MathematicalMedicine/DIVER/issues/122)).
* One missing bit of description text is now in. (Coincidentally, this was also on the View Variable page).
* Creating a Compound Cohort should now properly use the cohort tree view ([#106](https://github.com/MathematicalMedicine/DIVER/issues/106)).
* It *should* no longer be possible to get only counting information when attempting to Download Data ([#124](https://github.com/MathematicalMedicine/DIVER/issues/124)).


## 2023-03-20 16:05:29-0400
(diverweb 0.37.0, diverRPC 0.19.1, db\_procs 0.16.2, db\_edit 28)

* The Great Reordering: menu bar and dashboard have been rearranged to fit what we believe is the expected workflow order for new and existing users.
* As part of that reordering, Variable Sets and Custom Variables now have "landing pages" from which all functionality is accessible (much like Cohorts already do).
* Description text (Jo's draft of same) has been added to all user-visible pages (or at least it *should* be all user-visible pages; if any "lorem ipsum" is found, that's a bug).


## 2023-03-16 16:40:59-0400
(diverweb 0.36.2, diverRPC 0.19.0, db\_procs 0.16.2, db\_edit 28)

* Description text on the front page ("DIVER Dashboard") updated and Variables Catalog added to the list of front-page-advertised functionality.
* Some unimplemented functionality now has more useful and descriptive error messages indicating such.


## 2023-03-15 14:55:29-0400
(diverweb 0.36.1, diverRPC 0.18.0, db\_procs 0.16.1, db\_edit 28)

* All codebooks are now uploaded, and all PDF view links should now function.


## 2023-03-15 13:50:50-0400
(diverweb 0.36.1, diverRPC 0.18.0, db\_procs 0.16.1, db\_edit 28)

* "ALL\_EXISTS" cohorts and variable sets - automatically-generated artefacts of backend processing - are no longer being shown.


## 2023-03-14 15:53:47-0400
(diverweb 0.36.1, diverRPC 0.18.0, db\_procs 0.16.0, db\_edit 28)

* PDF view is up and running, with a few codebooks. (DIGS 1.0, DIGS 2.1MGS, DIGS 2.2MGS, DIGS 3.0r7) ([#12](https://github.com/MathematicalMedicine/DIVER/issues/12))
* Line breaks in question text are now rendered correctly.
* Other small details in viewing details of a variable (instrument indicated, less wasted whitespace, et cetera).
