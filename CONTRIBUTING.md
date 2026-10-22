# Contributing to AIDroneMap

Thank you for your interest in AIDroneMap. Bug reports, fixes, documentation, test datasets, benchmarks and new connectors are all welcome, from first-time contributors as much as from experienced ones.

This guide applies to every repository in the AIDroneMap organization unless a repository has its own `CONTRIBUTING.md`.

## Before you start

AIDroneMap is at an early stage, so things move quickly. To avoid wasted work:

- **Small fixes** (a typo, a clear bug, a missing test): open a pull request directly.
- **Anything larger** (a new feature, a change to the API, a new dependency, a refactor): open an issue first and describe what you want to do and why. A maintainer will reply before you invest time in code.
- **Questions and ideas**: open a discussion in the relevant repository.

Search existing issues and pull requests first. Someone may already be working on the same thing.

## Ways to contribute

- **Report a bug.** Include the AIDM version or image tag, the command or API call you used, the processing options, the error output, and the size of the dataset (image count and camera). A link to a small dataset that reproduces the problem helps most of all.
- **Fix a bug or build a feature.** See the workflow below.
- **Improve the documentation.** Clear instructions matter as much as code.
- **Share test data.** Datasets that expose a bug or a slow stage are valuable. Please read the section on datasets first.
- **Run benchmarks.** Timings on your hardware, with the method written down, help us check our claims.
- **Write a connector.** The cloud layer adds each compute provider as a small plugin. If you use a provider we do not support yet, a connector is a good self-contained contribution.

## Workflow

1. **Fork** the repository and clone your fork.
2. **Create a branch** from `main` with a short descriptive name, for example `fix/exif-altitude-parsing` or `feat/runpod-connector`.
3. **Make your change.** Keep each pull request to one logical change. Several small pull requests are easier to review than one large one.
4. **Add or update tests.** Bug fixes need a test that fails without the fix. New features need tests that cover them.
5. **Update the documentation** if your change affects behaviour, options or configuration.
6. **Commit with a sign-off** (see below) and push to your fork.
7. **Open a pull request** against `main`. Describe what changed, why, and how you tested it. Link the related issue.

## Commit messages

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
fix(exif): parse RTK altitude values with decimals
feat(cloud): add Runpod connector
docs: explain split-merge options
```

The first line says what the commit does, in under 72 characters. Add a body when the reason is not obvious from the change itself.

## Sign your commits (DCO)

Every commit must carry a `Signed-off-by` line. It certifies that you wrote the change, or otherwise have the right to submit it, under the project's open source licence, as described in the [Developer Certificate of Origin](https://developercertificate.org/).

Add it automatically with `-s`:

```
git commit -s -m "fix(exif): parse RTK altitude values with decimals"
```

This adds a line with the name and email from your git configuration:

```
Signed-off-by: Your Name <you@example.com>
```

If you forgot, sign the last commit with `git commit --amend -s`, or every commit on your branch with `git rebase --signoff main`, then force-push your branch. Pull requests with unsigned commits cannot be merged.

We do not ask you to sign a contributor licence agreement. You keep the copyright on your contribution.

## Licence

Your contribution is licensed under the licence of the repository you contribute to, shown in its `LICENSE` file. The AIDM engine is licensed AGPL-3.0, like the ODX code it is forked from. Do not copy code from sources whose licence is not compatible with the repository's licence. If you are unsure, ask in the pull request.

## What we look for in review

- **It works and it is tested.** CI must pass.
- **Claims are measured.** A change that says it makes processing faster or more accurate must include before and after numbers from the benchmark, on the same hardware and dataset.
- **Outputs stay compatible.** The task API and the output file layout are used by many tools. Changes to either need a discussion first.
- **It is understandable.** Clear names, comments where the reason is not obvious, and documentation for anything a user will see.
- **It stays focused.** Unrelated clean-ups belong in their own pull request.

## How review and merging work

A maintainer reviews every pull request. We may ask for changes; that is a normal part of the process, not a rejection. Small, focused pull requests get reviewed fastest.

For security, CI on pull requests from forks only runs after a maintainer approves it. If your checks show as waiting, that is why.

Maintainers merge approved pull requests, usually as a squash commit. Only maintainers can merge to `main`.

## Fixes that also apply to ODX

AIDM is forked from [ODX](https://github.com/WebODM/ODX) and syncs from it every week. If your fix applies to ODX too, consider sending it there as well, so the whole community benefits. We may suggest this in review.

## Test datasets

Drone images can show private property, people, vehicles or sensitive sites. Only share datasets that you have the right to share, and that you are happy to make public under an open licence.

- Do not commit images to a repository. Upload them somewhere public and link them in the issue or pull request.
- State the licence of the dataset, for example CC BY 4.0.
- Include the camera model, the image count and any ground control points.

## AI-assisted contributions

You may use AI tools to help write code or documentation. You remain responsible for every line you submit: read it, understand it, test it, and make sure you have the right to contribute it. Please mention in the pull request if a large part of it was generated.

## Reporting security issues

Do not open a public issue for a security vulnerability. Use the **Report a vulnerability** button in the repository's **Security** tab, which sends a private report to the maintainers.

## Behaviour

Be respectful and assume good faith. Critique code, not people. We want AIDroneMap to be a welcoming project for contributors from every background and level of experience.

Thank you for helping build AIDroneMap.
