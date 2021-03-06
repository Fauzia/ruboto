Subject: [ANN] Ruboto 0.16.0 released!

The Ruboto team is pleased to announce the release of Ruboto 0.16.0.

Ruboto (JRuby on Android) is a platform for developing full stand-alone
apps for Android using the Ruby language and libraries.  It includes
support libraries and generators for creating projects, classes, tests,
and more.  The complete APIs of Android, Java, and Ruby are available to
you using the Ruby language.

New in version 0.16.0:

In this release we add support for Android 4.4 KitKat!  You can also use
git-based gems in your Gemfile.apk, and implement framework methods like
onCreate in a Ruby Module and share them across Ruby classes.  We have
expanded the Android Fragment support to allow the use of the Ruboto
Widget DSL.  On the testing side, "ruboto setup" now downloads and
installs HAXM which gives a 10 times speedup of the emulator!  For early
adopters we now support Ruby 2.1 when using JRuby 9000 builds.

Features:

* Issue #479 rake log
* Issue #491 Add support for git-based gems
* Issue #495 Send all script names to be reloaded in one intent to speed
  up reload
* Issue #497 Allow implementing framework methods like onCreate and
  onResume in a Ruby module only.
* Issue #498 Allow use of Ruboto Widget in fragments
* Issue #499 Add shortcut "-t" for the "--target" option for "ruboto gen
  app"
* Issue #502 Use "ruboto emulator" to set up HAXM
* Issue #503 Add "rake boing" as alias for "rake update_scripts:reload"
* Issue #512 Ruby 2.1 support
* Issue #517 Generate AVD with new format when running "ruboto emulator"
* Issue #521 Add support for running emulator with Android 4.4 api level
  19
* Issue #526 Add KitKat (4.4) support

Bugfixes:

* Issue #438 Updating android_api.xml breaks test ruboto_gen_test
* Issue #448 Gems added from git repositories with the Gemfile.apk go
  unrecognized.
* Issue #484 "ruboto setup" doesn't work on mac
* Issue #494 Ensure that the app is running before triggering reload of
  scripts on device/emulator
* Issue #496 require 'ruboto/activity' from 'ruboto/activity/reload' since
  we depend on it.
* Issue #504 Sporadically missing instance variable
* Issue #509 Ruboto setup fails on windows with -y option
* Issue #511 "ruboto update app" should rebuild JRubyAdapter.java based on
  "ruboto.yml"
* Issue #516 Spinner#adapter returns nil when used with the :adapter
  option
* Issue #519 Spinner should have prettier layout

Support:

* Issue #522 rake BUILD FAILED - Windows and Linux

Documentation:

* Issue #492 Add tutorial for using fragments
* Issue #493 README proofreading changes
* Issue #508 Add AppSurfer as a sponsor.
* Issue #514 Remove the 'ruboto update ruboto' command.  Use 'ruboto
  update app' instead.
* Issue #515 Add a "Contributors Wanted!" banner to the home page.
* Issue #518 Sqlite_ar tutorial no longer works?

Pull requests:

* Issue #458 Changed gem_paths to work with a gem pointing to repository
  git in Gemfile.apk

Internal:

* Issue #466 Need faster tests for Travis-CI

Other:

* Issue #478 rake debug problem on Windows
* Issue #510 Ruboto setup on Windows fails to set path to dx

You can find a complete list of issues here:

* https://github.com/ruboto/ruboto/issues?state=closed&milestone=30


Installation:

To use Ruboto, you need to install a Ruby implementation.  Then do
(possibly as root/administrator)

    gem install ruboto
    ruboto setup

To create a project do

    ruboto gen app --package <your.package.name>
    cd <project directory>
    ruboto setup

To run an emulator for your project

    cd <project directory>
    ruboto emulator

To run your project

    cd <project directory>
    rake install start

You can find an introductory tutorial at
https://github.com/ruboto/ruboto/wiki

If you have any problems or questions, come see us at http://ruboto.org/

Enjoy!


--
The Ruboto Team
http://ruboto.org/
