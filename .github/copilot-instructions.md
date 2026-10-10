# Copilot instructions for list

## Project snapshot

- The repository contains an English and Portuguese step-by-step tutorial (`README.md` and `README-pt-BR.md`) and the tutorial's Laravel application under `src/`.
- The application is Laravel 13 (PHP ^8.3) with Laravel Breeze-style Blade authentication/profile pages, Vite, Tailwind CSS, and Alpine.js.
- The intended database for the tutorial is MySQL; the project owner has a local MySQL installation. The current `src/.env.example` still defaults to SQLite, and PHPUnit tests use an in-memory SQLite database. Keep this distinction clear when documenting or changing database setup.

## Build, test, and lint commands

- Run Laravel commands from `src/`, where `artisan`, `composer.json`, and `package.json` live.
- `composer setup` installs PHP and JavaScript dependencies, creates the local environment file/key, migrates, and builds assets.
- `composer dev` starts the Laravel development process; `npm run dev` starts Vite by itself.
- Run the PHP test suite with `composer test` or `php artisan test`. Run one test file with `php artisan test tests/Feature/ProfileTest.php`, or select a test by name with `php artisan test --filter=test_profile_page_is_displayed`.
- Format/check PHP style with `vendor/bin/pint` / `vendor/bin/pint --test`.
- Build frontend assets with `npm run build`. `package.json` has no lint script.
- When documenting commands, state that they run from `src/` and keep them consistent with the Laravel app version and earlier tutorial steps.

## High-level architecture

- `src/` is a conventional Laravel app: `routes/web.php` defines web and authenticated profile/dashboard routes and includes `routes/auth.php`; controllers and form requests live under `app/Http/`; Blade layouts, components, and pages are under `resources/views/`.
- Authentication and profile management are the current functional baseline. Feature tests under `tests/Feature/` exercise these flows using `RefreshDatabase`; PHPUnit is configured for SQLite `:memory:`.
- Composer scripts define application setup, development, and testing; npm/Vite handles CSS and JavaScript assets.
- Treat the README files as a chronological, reproducible tutorial describing how this app was created. Keep tutorial steps consistent with the current source while preserving the order needed to recreate it.

## Key conventions

- Keep `README.md` and `README-pt-BR.md` aligned in tutorial steps and outcomes.
- Run commands that target the Laravel application from `src/`; distinguish them from repository-level documentation changes.
- Follow the existing Laravel patterns: web routes delegate nontrivial behavior to controllers, request validation uses form request classes, and UI is composed from Blade views/components.
- Preserve the test database isolation in `phpunit.xml`; do not require local MySQL credentials to run the test suite.
- Use placeholders for local MySQL settings; never put machine-specific credentials in tracked docs or configuration.
- Before changing Laravel application code, follow the setup and generated guidance in `src/AGENTS.md` and `src/CLAUDE.md` (including Laravel Boost setup when required).
