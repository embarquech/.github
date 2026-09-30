# Security policy

This policy covers every Cryptnox repository on GitHub without its own — the command line tools, the SDKs, the card documentation and the supporting tools published by Cryptnox SA.

There is no paid bug bounty. We take every report seriously, work with you on the fix, and credit you publicly if you wish.

## Reporting

Do not report security problems through public issues, pull requests or discussions.

Email **security@cryptnox.com**, encrypting your report and any proof of concept with the Cryptnox security key:

```
Security Cryptnox <security@cryptnox.com>
ed25519 / cv25519, valid until 2029-09-29
Fingerprint: 1D6D 6902 5F93 15DE FB56  A947 3606 ACE6 6D84 24B1
```

<details>
<summary>Public key</summary>

```
-----BEGIN PGP PUBLIC KEY BLOCK-----

mDMEaruKphYJKwYBBAHaRw8BAQdAiMb/k5Ru0GRCjsFOj+XdLsH6ksV4r3baC9ha
2RYm6BS0KVNlY3VyaXR5IENyeXB0bm94IDxzZWN1cml0eUBjcnlwdG5veC5jb20+
iJkEExYKAEEWIQQdbWkCX5MV3vtWqUc2BqzmbYQksQUCaruKpgIbAwUJBaTtegUL
CQgHAgIiAgYVCgkICwIEFgIDAQIeBwIXgAAKCRA2BqzmbYQksZuVAQDiSZKPyLD3
Tzs72aLoaAw0hKhdrIA8wLlnxpbugMZ5CwD/V5RmgtvfpN8+AtBEzwGRKJuGteej
d89pRzPKjHVC6AW4OARqu4qmEgorBgEEAZdVAQUBAQdALx8S16QtncMPEyenqwzn
gQ7YTnbtrOYjL33IBaP4mBkDAQgHiH4EGBYKACYWIQQdbWkCX5MV3vtWqUc2Bqzm
bYQksQUCaruKpgIbDAUJBaTtegAKCRA2BqzmbYQksdCsAQCrvqTTKCarW5Z+YPh+
rXMyhPUOsUY/TrKOpd4lXNzrcAD+OUdM0zuMKXQLTACumVH0bWTI1fIhVPIB8pM+
SiHw/AY=
=WPay
-----END PGP PUBLIC KEY BLOCK-----
```

</details>

Check the fingerprint before you use the key; include your own public key to get an encrypted reply. Where a repository shows a Report a vulnerability button (Security → Advisories), GitHub's private vulnerability reporting is an alternative, but encrypted email is preferred for working exploits or card secrets.

Include the problem and its impact, the affected versions (package or commit, and card model and firmware if a card is involved), a proof of concept, and the name or pseudonym to credit. English, ideally a Markdown file, with traces or screenshots as needed. **Never send real PINs, PUKs, keys or seeds — use test cards.**

If you send a patch with your report, it can only be merged once you have accepted the [Cryptnox Contributor Agreement, version 1.1](https://github.com/embarquech/.github/blob/contributor-agreement-v1.1/CONTRIBUTOR_AGREEMENT.md), as for any other contribution. You accept by writing "I accept the Cryptnox Contributor Agreement, version 1.1" in the advisory or in your email.

## Scope

- **Command line tools and SDKs** published in these repositories, including the released packages: how they open and use the secure channel, verify the card, build the commands and present the results.
- **Card applet security.** The Java Card applets are closed-source, but flaws in their security — key protection, the PIN, the secure channel, card authentication — are in scope, whether found through the tools or by testing a card.

Examples, documentation and internal tooling are not a focus; report anything serious there as a normal bug.

### Properties we protect

Breaking one of these is what we consider most serious.

- **Key confidentiality.** Private keys and seeds cannot be read out, except through a backup the user deliberately starts.
- **PIN protection.** The PIN cannot be bypassed, and the number of PIN attempts is limited.
- **Signing integrity.** The card signs only with the user's authorisation, and the software sends the card what the user was shown — the transaction, message, address or derivation path.
- **Secure channel.** Traffic between the software and the card cannot be read or altered by a third party on the reader, the USB or NFC link, or the host card stack.
- **Card authenticity.** The software tells a genuine Cryptnox card from a counterfeit or tampered one.
- **Software integrity.** Published packages and releases cannot be altered on the way to the user.

### Attacker we assume

A hostile link (a malicious reader, an NFC eavesdropper, or host software between the tools and the card), physical possession of the card without the PIN, and supply-chain tampering with a card, package or dependency.

A card has no screen: the host software is where the user sees what will be signed, so a fully compromised host is a stronger attacker than for a wallet with a display. Reports that assume a compromised host are welcome; their severity depends on what the attacker gains beyond that host control.

## Valid reports

- **Demonstrated, not theoretical** — a script, test, APDU trace or reproduction on a test card; side channels and fault attacks need measurements. Exception: code meant to enforce a security property that visibly fails to (a missing check, a secret-dependent branch in constant-time code) needs no demonstration.
- **Against the current version** — the latest package, and the latest card firmware if a card is involved. Forcing a user onto a vulnerable older version is itself valid.
- **Fixable by Cryptnox** — not an attack no change to our software or cards could prevent (a camera filming the PIN, say).
- **Not an easier route** to a result already reachable with equal or weaker preconditions.

### Out of scope

Phishing and social engineering; unverified scanner or language-model output; outdated dependencies or weak TLS without demonstrated impact; denial of service, including bricking your own card with wrong PINs; attacks that need the PIN or a fully unlocked host to do what that access already allows; third-party projects Cryptnox does not operate; and Cryptnox websites and online services (report to the same address, handled outside this policy).

## Testing and disclosure

Test in good faith: use your own cards and keys, go no further than needed to prove the issue, do not disrupt services or other users, and give us time to fix before disclosing. We will not take legal action against anyone who follows this policy.

After a report we acknowledge it (normally within five working days), reproduce and assess it, develop a fix — privately where disclosure would reveal the issue — and publish an advisory crediting you if you wish. We ask for **90 days** before public disclosure unless we agree otherwise; card-firmware fixes can take longer, as they go through production.

We may close reports that miss these criteria or are out of scope, and may decline to work with anyone who threatens early disclosure or asks for payment as a condition of the report.

Thank you for helping keep Cryptnox users safe.
