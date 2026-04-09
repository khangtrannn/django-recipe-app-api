# Copilot Instructions

This repository follows the "Build a Backend REST API with Python & Django" course codebase. When generating inline suggestions, stay close to the current chapter and the existing patterns in this repo.

## Project Context

- Use Django 3.2-compatible code and the dependencies already listed in `requirements.txt`.
- Prefer incremental changes that match the current learning step instead of jumping ahead to later architecture.
- Keep suggestions aligned with what already exists in the repo: Django app structure, custom management commands, model tests, and simple helper methods.

## Style And Conventions

- Use single quotes for Python strings.
- Prefer clear, small functions and classes over abstractions that are not already used in the repo.
- Preserve the existing file style when editing; do not reformat unrelated code.
- Use 4 spaces for Python indentation in new code.
- Keep comments and docstrings short and practical.

## Django Patterns To Prefer

- For custom users, follow the course pattern: `AbstractBaseUser`, `PermissionsMixin`, a custom manager, `email` as `USERNAME_FIELD`, and `normalize_email()` in `create_user()`.
- For commands, prefer `BaseCommand`, `self.check(databases=['default'])`, and explicit handling for `psycopg2.OperationalError` and `django.db.utils.OperationalError`.
- For tests, prefer `TestCase`, `SimpleTestCase`, `unittest.mock.patch`, and direct assertions that match the course examples.
- Keep model and command code simple and explicit rather than DRF-heavy unless the surrounding files already use DRF.

## Development Workflow

- Prefer the repo’s Docker commands when describing how to run code or tests, for example:
  - `docker-compose run --rm app sh -c "python manage.py test"`
  - `docker-compose run --rm app sh -c "flake8"`
  - `docker-compose run --rm app sh -c "python manage.py wait_for_db"`
- If a suggestion depends on a missing file or later lesson, keep the suggestion minimal and avoid inventing extra layers.

## Inline Suggestion Goal

- Make suggestions that continue the current file naturally.
- Prefer code that completes the exact pattern already started in the repository.
- Avoid proposing unrelated refactors, alternate frameworks, or advanced patterns unless the user explicitly asks for them.
