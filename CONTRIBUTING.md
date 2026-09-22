# Contributing to Cryptnox projects

Bug reports, fixes and improvements are welcome. This file applies to every repository of the cryptnox organisation that does not have a CONTRIBUTING.md of its own. It has two parts: how to work on the code, and the terms under which Cryptnox SA accepts contributions. Please read both before you open a pull request.

## Working on the code

Setup, tests and other checks differ between projects. The README of each repository describes them, and some repositories have a CONTRIBUTING.md of their own with more detail.

Branch from `main` and open a pull request against `main`. Say in the pull request what you changed, why, and how you tested it. If hardware was involved, name the card and reader you used, or say that you could not test on hardware.

Never commit keys, certificates with private keys, or other card material.

### Third-party code and dependencies

Do not paste code from another project into a pull request unless you say so in the description, name the source and its licence, and keep its licence header. Only permissively licensed code (MIT, BSD, Apache-2.0) can be accepted. Code and new dependencies under the GPL or AGPL cannot be accepted, because they cannot be shipped under the commercial licence.

## Contribution terms

Most Cryptnox projects are dual licensed: an open source licence for everyone, and a commercial licence that Cryptnox SA sells to customers who cannot work with the open source licence. Cryptnox can only offer the commercial licence if it holds the necessary rights in all of the code, so every contributor from outside Cryptnox is asked to accept the [Cryptnox Contributor Agreement](https://github.com/embarquech/.github/blob/main/CONTRIBUTOR_AGREEMENT.md) before a pull request is merged.

In short: you transfer the copyright in your contribution to Cryptnox SA, you get back a licence to do whatever you like with your own work, your contribution stays available as open source, and you are credited by name in the project's AUTHORS.md, in the git history and in the changelog. The agreement itself is the binding text.

You accept the agreement by ticking the contribution terms box in the pull request template, once for each pull request. Maintainers will not tick it for you, and a pull request without it cannot be merged, however small the change.

If you cannot accept the agreement, you can still help: describe the bug or the fix in an issue, without code, and a maintainer can implement it. Questions about the agreement go to contact@cryptnox.com.
