# Axel's Renovate configuration

A shared Renovate preset for most of my projects.

## Features

* Starts from the [best-practices preset](https://docs.renovatebot.com/presets-config/#configbest-practices)
* Enforce a minimum release age of 7 days
* Only creates PRs when the minimum release age is met
* Creates a Dependency Dashboard
* Auto-merges
    * [stable non-major releases](https://docs.renovatebot.com/presets-default/#automergestablenonmajor) (i.e. not
      0.x.x, not 1.x.x to 2.x.x)
    * [digest updates](https://docs.renovatebot.com/presets-default/#automergedigest)
    * lock-file maintenances
    * dependencies pin
* Pin versions for production dependencies
* Provides changelog for [GitHub Actions digest updates](https://www.jvt.me/posts/2025/05/08/renovate-digest-changelog/)

## Required repository configuration

To prevent Renovate from merging even if its own checks failed, a branch protection rule must set to only allow merges
when the following checks are successful:

* The CI workflow(s)
* renovate/artifacts
* renovate/stability-days
