# Contributing to the HPC Workforce Development and Retention Website

If you are comfortable working with forks, branches, and pull requests, please
follow the below guidance. If you are not, please reach out to the @hpc-wdr-admin team.

The general workflow for everyone interacting with the HPC-WDR website
is described in the following.

## Contents

1. [Introduction](#introduction)
   1. [Forking](#forking)
   1. [Keeping Your Fork Updated](#keeping-your-fork-updated)
1. [Creating Issues](#creating-issues)
   1. [Markdown](#markdown)
1. [Working on Issues](#working-on-issues)
   1. [When Work Begins](#when-work-begins)
   1. [As Work Continues](#as-work-continues)
   1. [When Work is Complete](#when-work-is-complete)
   1. [Closing Old Issues](#closing-old-issues)
1. [Pull Requests](#pull-requests)
   1. [Automated Tests](#automated-tests)
   1. [Reviewers](#reviewers)
   1. [Work-in-Progress](#work-in-progress)
   1. [Merging](#merging)

## Introduction

We recommend using a `fork` and `branch` approach to contribution. In this method,
you will create a personal fork of the main HPC-WDR website repository,
make your changes locally in your own branches, and then open pull
requests to merge changes back into the main repository.

[↑ Contents](#contents)


### Forking

To create a fork, go to the [main repository](https://github.com/HPC-Workforce-Development-and-Retention/hpc-wdr)
and click the `Fork` button in the top-right. You can choose under what username
or organization the fork is made; we recommend your personal account.

After it's creation, you will now have a local fork of the repository.

See [GitHub's Documentation](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
for more details.

[↑ Contents](#contents)


### Keeping Your Fork Updated

After your fork is created, you will need to make sure it stays up-to-date to
avoid conflicts when you make changes.

See [GitHub's Documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)
for the various ways to keep your fork in sync.

[↑ Contents](#contents)


## Creating Issues

[Create issues in GitHub](https://github.com/HPC-Workforce-Development-and-Retention/hpc-wdr/issues)
for any work that needs to be done. This can include, but is not limited to:

- Contributing content (blogs, events, etc.)
- Bugs
- Enhancements
- Discussions

[↑ Contents](#contents)


### Markdown

[Markdown](https://en.wikipedia.org/wiki/Markdown) is a lightweight markup
language with plain text formatting syntax.  GitHub uses a form of it for
rendering issue and pull request descriptions and comments, wiki pages, and
any files in your repositories with a `.md` extension (such as this one).  For
more details on what's possible with GitHub-flavored Markdown, [see GitHub's
documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

[↑ Contents](#contents)


## Working on Issues

### When Work Begins

Make sure your local `main` branch is up-to-date by running

```bash
git checkout main
git pull remote main
```

> **Note:**  You should not make commits on your `main` branch, as
> all changes will be making it into `main` via [pull requests](#pull-requests).

Once `main` is updated, you then create a feature branch off of it with `git
checkout -b <branchName>`.  

We recommend using the format `username/description` when naming the branch
for clarity on who is doing the work and what type of work is being completed.
For example, `mrmundt/update-contributing`.

[↑ Contents](#contents)


### As Work Continues

Do whatever work is necessary to address the issue you're tackling. Divide your
work into logical, compilable commits. Feel free to commit small chunks of
work early and often in your local repository.

[↑ Contents](#contents)


### When Work is Complete

While working on your feature in your local repository, other commits likely
made it into the remote `main` branch. There are a variety of ways to merge
these changes into your local feature branch. One possibility is:

```bash
git checkout main
git pull --ff-only
git checkout <branchName>
git rebase main
```

though there are others that are equally valid.

Once you are done, [create a pull request](#pull-requests).

[↑ Contents](#contents)

### Closing Old Issues

If at any point you encounter an issue that will not be worked in the
foreseeable future, it is worthwhile to close the issue such that you can
maintain a reasonable backlog of upcoming work. Be sure to include in the
comments some explanation as to why the issue won't be addressed.

[↑ Contents](#contents)


## Pull Requests

When making a pull request contribution, it is important to properly communicate the
gist of the contribution. If it is a simple code or editorial fix, simply
explaining this within the pull request will suffice. However, if this
is a larger fix or enhancement, it should be first discussed with the project
leader or developers. You can [open an Issue](#creating-issues) using the
appropriate template, visit the HPC-WDR #website Slack channel, or email
[contact@hpc-wdr.org](mailto:contact@hpc-wdr.org), to name a few options.

The preferred way changes get into `main` is through pull requests.  When you've
completed work on an issue, push your branch to the remote with `git push -u
<remoteName> <branchName>`, and then create a pull request.

The repository comes with a [pull request template](PULL_REQUEST_TEMPLATE.md)
that provides you with a checklist and helpful reminders for these points.

1. All pull requests should be sent to the `main` branch, unless you are testing an integration,
   in which case you should cc @hpc-wdr-admin in an issue.
2. Follow the existing code style precedent.
3. Test and preview your pull request locally (see the
   [README](https://github.com/HPC-Workforce-Development-and-Retention/hpc-wdr/blob/main/README.md) for more details)
4. If necessary, update the `README.md`.
5. In addition to reviews, any automated tests must pass before a pull request will be merged.

[↑ Contents](#contents)


### Reviewers

We recommend having your pull request reviewed by at least two people:

- A specified reviewer for content (e.g., a collaborator, etc.)
- A member of the @hpc-wdr-maintainers team

[↑ Contents](#contents)


### Automated Tests

There are currently two automated tests:

1. URL Checker: This test ensures that URLs within the repository all work.
   If there is a real failure, the URL will need to be fixed (or removed, as
   appropriate). If it is a temporary failure, the job can be re-run. If a
   particular URL or file should be ignored, this can be added to the
   [configuration](https://github.com/HPC-Workforce-Development-and-Retention/hpc-wdr/tree/main/.github/workflows/linting.yaml) of the workflow.
2. Spell Checker: This test looks for common misspellings and will error if it
   detects one. The typo will need to be fixed or, if it is a false failure
   (e.g., names will sometimes cause failures), words to be ignored can be added to the
   [configuration file](https://github.com/HPC-Workforce-Development-and-Retention/hpc-wdr/tree/main/.github/workflows/typos.toml).

[↑ Contents](#contents)


### Work-in-Progress

You may wish to have your changes reviewed by colleagues before they are ready
to be merged into `main`.  To do so, create a pull request as usual, but
insert "[WIP]" at the beginning of the Title.

You may also create a "Draft" request
(see [GitHub's documentation](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests#draft-pull-requests)).

GitHub will not allow you to merge a Draft or WIP request.

[↑ Contents](#contents)


### Merging

When the reviews are finished and all changes approved, your pull request will
be merged by a member of @hpc-wdr-maintainers.

[↑ Contents](#contents)
