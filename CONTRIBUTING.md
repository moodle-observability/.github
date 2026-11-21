# Contributing to Moodle Observability

Thanks for your interest in contributing! This guide applies to every repository in the [moodle-observability](https://github.com/moodle-observability) organization unless a repository has its own `CONTRIBUTING.md`.

## Supported versions

- **Moodle 5.3 and later.**
- PHP and database versions supported by the targeted Moodle release (see the [Moodle release notes](https://moodledev.io/general/releases)).
- CI runs against **PostgreSQL** and **MariaDB**.

## Before you start

1. Search the existing issues. If none covers your change, open one using the bug report or feature request template.
2. For larger changes, discuss the approach in the issue before writing code.
3. Issues labeled `good first issue` are a good place to start; `help wanted` marks issues where we would especially appreciate help.

## Coding standard

All code must follow the [Moodle coding style](https://moodledev.io/general/development/policies/codingstyle), enforced by [moodle-cs](https://github.com/moodlehq/moodle-cs) (PHP_CodeSniffer):

- Frankenstyle naming (`tool_<name>`), namespaced classes under `classes/` with autoloading.
- Complete PHPDoc blocks and the GPL license header in every PHP file.
- All user-facing strings in `lang/en/<component>.php`; never hard-coded.
- Use the Moodle APIs (DML, Output/Mustache, Task, Cache/MUC, Privacy, Messaging) instead of raw PHP equivalents.
- Never store or send personal data without a matching [Privacy API](https://moodledev.io/docs/apis/subsystems/privacy) provider. Metrics and traces must not contain PII.
- Third-party libraries must be listed in `thirdpartylibs.xml`.

Run the checks locally with [moodle-plugin-ci](https://moodlehq.github.io/moodle-plugin-ci/):

```bash
moodle-plugin-ci phplint
moodle-plugin-ci phpcs --max-warnings 0
moodle-plugin-ci phpdoc
moodle-plugin-ci validate
moodle-plugin-ci savepoints
moodle-plugin-ci mustache
moodle-plugin-ci grunt --max-lint-warnings 0
moodle-plugin-ci phpunit --fail-on-warning
moodle-plugin-ci behat
```

You can also run the GitHub Actions workflow locally with [act](https://github.com/nektos/act).

## Pull request workflow

1. Fork the repository and create a branch from `main` (e.g. `issues/42`).
2. Make focused commits. We use [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `docs:`, `ci:`, `test:`, `refactor:`).
3. Add or update tests (PHPUnit and, for UI, Behat).
4. Bump `version.php` when the change requires an upgrade (DB schema, capabilities, tasks, caches) and add savepoints in `db/upgrade.php`.
5. Update the README and changelog when behavior changes.
6. Open a pull request using the template and link the issue (`Closes #42`).
7. Make sure **CI is green**. A maintainer will review; please address feedback in new commits.

## Continuous integration

Every repository runs `moodle-plugin-ci` on GitHub Actions for each push and pull request, with a matrix of supported Moodle branches (5.3+), PHP versions and databases (PostgreSQL, MariaDB). Pull requests are merged only when all checks pass.

The standard workflow is the organization template [`workflow-templates/moodle-plugin-ci.yml`](workflow-templates/moodle-plugin-ci.yml) (offered in *Actions > New workflow* of every repository). Copy it to `.github/workflows/ci.yml` and keep the job id `test`: the release scripts look for check runs named `test (...)`.

## Reporting security issues

Please **do not** open public issues for security vulnerabilities. Use GitHub's [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) on the affected repository instead.

## License

By contributing, you agree that your contributions will be licensed under the [GNU GPL v3 or later](https://www.gnu.org/licenses/gpl-3.0.html), the same license as Moodle.
