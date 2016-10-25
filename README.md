Version check pre-push hook for Git
===================================

Have you ever merged a pull request, and later realised you forgot to increment the version?
If you are practising continuous integration, an artifact might already be deployed by then!

This project contains an example of a pre-push hook for Git to prevent such accidents.
It is a check that runs at the exact moment you need to be reminded:
when you finish implementing your feature and type `git push`.

You will probably need to customise the script to fit your particular environment.
The version of the script included here supports the conventions for
[CommBank](https://github.com/CommBank] scala projects, namely:

  * All pull requests are made against `origin/master`
  * The file `version.sbt` contains the version string, and *no other settings that might change*


Usage
-----

To add this hook to your projects:

    # in the checkout directory of version-check-git-hook
    git config --global init.templatedir `pwd`/init.template

    # in each existing repo (no existing hooks will be overwritten)
    git init
