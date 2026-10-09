# Copilot instructions for list

## Project snapshot

- This repository documents how to build a Craigslist-inspired listing application through a step-by-step tutorial; the tutorial should let a reader reproduce the project by following its steps.
- The initial implementation stack is Laravel with MySQL. The project owner already has a local MySQL installation.
- This checkout currently contains only the documentation and license, not the Laravel application source or its dependency manifest. Treat Laravel as the tutorial's target, not as an already bootstrapped app.

## Build, test, and lint commands

- No project-defined build, test, or lint commands were found in this repository snapshot.
- Composer is installed in the project owner's local environment, although its executable may not be available on the current session's `PATH`.
- There is no `composer.json`, `package.json`, `phpunit.xml`, `artisan`, `.github/workflows`, or other automation config currently present.
- When documenting commands for the tutorial, make clear which working directory they run from and keep them consistent with the Laravel version and files created in preceding steps.
- Do not add application build/test commands as repository commands until the corresponding app and configuration exist.

## High-level architecture

- The README is intended to be a chronological, reproducible guide to creating the application, rather than only a project overview.
- The target application is built with Laravel and uses MySQL as its initial database.
- Since no application code exists in this checkout, the tutorial is the source of truth for the intended architecture as it is established. Keep each step consistent with prior steps and the resulting Laravel project structure.
- The local MySQL installation is an available prerequisite; tutorial setup should explain the database connection/configuration needed by Laravel without assuming or publishing local credentials.

## Key conventions

- Keep `README.md` and `README-pt-BR.md` aligned as the tutorial evolves; preserve matching steps and outcomes across the English and Portuguese versions.
- Write tutorial steps in the order a reader needs to perform them, including required configuration and commands, so following the guide produces the same result.
- Do not assume a Laravel app exists in the repository until its source and bootstrap files are added. Distinguish commands run inside the tutorial-created app from commands run in this documentation repository.
- Do not include real machine-specific database credentials in documentation; use clearly identified local configuration placeholders.
