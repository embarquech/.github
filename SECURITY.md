# Security policy

This policy applies to every repository of the cryptnox organisation on GitHub that does not have a security policy of its own: the command line tools, the SDKs and the supporting tools published by Cryptnox SA.

## Reporting a vulnerability

Please do not report security problems through public issues, pull requests or discussions.

The preferred way is GitHub's private vulnerability reporting. On the repository page open the Security tab, choose Advisories and click Report a vulnerability. Only the maintainers see the report, and the discussion and the fix stay private until an advisory is published.

If the repository shows no Report a vulnerability button, or you have no GitHub account, send an email to contact@cryptnox.com with "Security" in the subject line.

Please include:

- the repository and the version affected (package version or commit),
- the card model and firmware version, if a card is involved,
- steps to reproduce or a proof of concept,
- the impact as you see it,
- how you would like to be credited, if at all.

Never include real PINs, private keys, seed phrases or other card secrets in a report. Use test cards and test keys.

## What happens next

Cryptnox acknowledges the report, confirms the problem together with you, prepares a fix and publishes a security advisory on the repository with the fix and, if you wish, your name as the reporter. Please give Cryptnox reasonable time to release a fix before publishing anything about the problem, and tell us your own disclosure timeline when you report.

## Scope

Everything in the Cryptnox repositories is in scope. The card firmware and applets are not published in these repositories, but a problem in a card that you find through these tools can be reported the same way.

Problems in third-party dependencies belong to that project. Please tell us as well if the Cryptnox software is affected.

Testing done in good faith, on your own cards and accounts, without accessing other people's data and without disrupting services, is welcome.

## Supported versions

Security fixes go into the latest release of each package. Please update to the latest version before reporting, where you can.
