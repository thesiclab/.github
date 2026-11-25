# Contributing to The SiC Lab

Thanks for wanting to help. This file applies to every repository in the thesiclab organization, unless a repository has its own CONTRIBUTING file.

## How the lab works

The SiC Lab is one human, Dan, and one AI, Mabus.

- **Dan** picks the problems, makes the calls, reviews every pull request and merges it.
- **Mabus** drafts, builds and opens pull requests. Mabus never approves or merges anything, including its own work.

Pull requests from Mabus are reviewed and merged by Dan, the same as yours. There is no one else on the team, so reviews can take a few days. That is not a sign we are ignoring you.

## Before you start

- **Small fix** (a typo, a broken link, an obvious bug): open a pull request straight away.
- **Anything bigger:** open an issue first, using the Bug report or Idea form. Say what you plan to do. This saves you from building something we cannot take.
- **Security problem:** do not open an issue or a pull request. Follow [SECURITY.md](SECURITY.md).

Two of our repositories are public: [sic-pr-caddie](https://github.com/thesiclab/sic-sic-pr-caddie) and this one. The others are private for now, so outside contributions can only go to the public ones.

## Branches

- Nobody pushes to `main`. Every change lands through a pull request.
- Outside contributors: fork the repository and work on a branch in your fork.
- Use a short branch name that says what the change is, for example `fix-guard-quoting` or `docs-install-steps`.
- Mabus uses branches named `mabus/<topic>`.
- Do not force-push a branch after review has started. Add new commits instead, so the reviewer can see what changed.

## Signed commits

Every commit must be signed and show as **Verified** on GitHub. You can sign with an SSH key, a GPG key or an S/MIME certificate. SSH is the simplest if you already push over SSH:

```sh
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
```

Then add the same public key to your GitHub account as a **Signing key** (not only as an authentication key). The email in your commits must be one that is verified on your GitHub account.

GitHub's guides:

- [About commit signature verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)
- [Telling Git about your signing key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)
- [Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

## Tests

Run the tests before you open a pull request, and say in the pull request what you ran.

| Repository     | Language                                   | How to test                                                     |
| -------------- | ------------------------------------------ | --------------------------------------------------------------- |
| sic-pr-caddie      | Python 3.8 or newer, standard library only | `python3 -m unittest`                                           |
| sicrules       | Python 3.11 or newer                       | `pip install -e '.[test]'` then `python -m pytest -q`           |
| edition-engine | TypeScript, Node 22, pnpm                  | `pnpm install --frozen-lockfile`, `pnpm test`, `pnpm typecheck` |

In sicrules, ten tests under `tests/lab/` read files that exist only on the lab machine, so they fail anywhere else. CI deselects exactly those ten; the workflow file lists them.

A change that fixes a bug should add a test that fails without the fix. A change that adds behaviour should add tests for it. If you cannot test something, say so and say why.

Each repository's README, AGENTS.md or CONTRACT.md may have more rules. Read them before you change that repository.

## Pull requests

1. Keep one change per pull request. Smaller pull requests get reviewed sooner.
2. Fill in the pull request template: what, why, how you tested it, and whether it touches user data or secrets.
3. Link the issue it fixes, for example `Fixes #12`.
4. Make sure CI passes. If a check fails for a reason outside your change, say so in the pull request.
5. Never commit secrets: no API keys, tokens, passwords, `.env` files or private keys. If you commit one by mistake, tell us at once and treat the secret as leaked, even after you remove it.

Using an AI tool to write your change is fine. You are still responsible for the change: read it, test it, and be ready to explain it.

## Reviews

- Dan reviews every pull request. Mabus may leave comments, but Dan makes the decision.
- Dan may ask for changes. Push new commits to the same branch to answer them, and resolve each conversation when it is done.
- Pull requests are merged with **squash merge**, so your branch becomes one commit on `main`. Dan may edit the commit message.
- If we decide not to take a change, we will say why and close the pull request.

## License

Each repository has its own license in its LICENSE file. By contributing, you agree that your contribution is licensed under the license of the repository you contribute to.

## Code of Conduct

Everyone who takes part follows our [Code of Conduct](CODE_OF_CONDUCT.md).

## Questions

See [SUPPORT.md](SUPPORT.md).
