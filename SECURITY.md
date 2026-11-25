# Security policy

This policy applies to every repository in the thesiclab organization, unless a repository has its own SECURITY file.

## Report a vulnerability privately

Please do not report security problems in public issues, pull requests or discussions.

Use one of these two ways:

1. **GitHub private vulnerability reporting** (preferred, for public repositories). Open the repository's **Security** tab and click **Report a vulnerability**. Only you and the maintainers can see the report. GitHub's guide: [Privately reporting a security vulnerability](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability).
2. **Email** thesiclab@proton.me. Use this if the button is not there, or if the problem is not tied to one repository. Put "Security" in the subject line.

Please include:

- which repository and which version or commit
- what the problem is and what an attacker could do with it
- steps to reproduce it, or a proof of concept
- any fix or mitigation you know of

Do not include real secrets, tokens or other people's data in the report. If you found a leaked secret of ours, tell us where it is. Do not use it.

## Who reads it, and how fast

The SiC Lab is one human, Dan, and one AI, Mabus. Dan reads every report. Mabus may help look into it and draft a fix, but Dan decides what happens and merges every fix.

We are two, not a security team, so these are honest targets, not promises:

- **First reply:** within 7 days.
- **Our assessment** (whether we can reproduce it and how serious it is): within 14 days.
- **A fix:** depends on how serious it is and how hard it is to fix. We will tell you our plan and keep you updated.

If you have not heard back in 7 days, please send a reminder to the same address.

## Disclosure

We follow coordinated disclosure. Please give us a reasonable time to fix the problem before you make it public. We suggest 90 days from your report, and we will agree a date with you. When a fix is out, we publish a GitHub security advisory for public repositories, and we credit you unless you ask us not to.

We do not run a bug bounty and cannot pay for reports.

## Supported versions

All our projects are early and have no releases yet. We fix security problems only on the `main` branch of each repository.

| Repository     | Supported |
| -------------- | --------- |
| pr-caddie      | `main`    |
| sicrules       | `main`    |
| edition-engine | `main`    |
| .github        | `main`    |

When a project starts publishing releases, its own SECURITY file will say which versions get fixes.

## Scope

In scope: the code in thesiclab repositories.

Out of scope: problems in third-party services or dependencies (please report those to their owners, and tell us if one affects our code), and reports that need physical access to a user's machine or an already-compromised account.
