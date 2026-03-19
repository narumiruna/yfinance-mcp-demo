# Repository Guidelines

## Project Structure & Module Organization
This repository is intentionally small:
- `demo.py`: Chainlit demo app and MCP tool-calling flow.
- `pyproject.toml`: Python metadata, runtime dependencies, and dev tools.
- `README.md`: setup and usage instructions for contributors.
- `.chainlit/config.toml`: Chainlit runtime configuration.
- `.env.example`: environment variable template.

Keep new modules focused. If logic grows, move reusable code from `demo.py` into a small package directory (for example, `src/`), but only when duplication or complexity justifies it.

## Build, Test, and Development Commands
Use `uv` for all environment and execution tasks.

- `uv sync`: install runtime dependencies.
- `uv sync --group dev`: install development tools.
- `uv run chainlit run demo.py`: start the local chatbot at `http://localhost:8000`.
- `uv run ruff check demo.py`: run lint checks.
- `uv run ty check demo.py`: run type checks.

Run `ruff` and `ty` before opening a pull request.

## Coding Style & Naming Conventions
- Target Python `3.13` (see `pyproject.toml`).
- Use 4-space indentation and explicit type hints on public functions.
- Use `snake_case` for functions/variables, `UPPER_CASE` for constants, and concise verb-based function names.
- Keep functions small and single-purpose; avoid speculative abstractions.
- Prefer clear comments only where behavior is non-obvious.

## Testing Guidelines
There is no formal test suite yet. Current quality gates are linting and type checking.

When adding tests:
- place them under `tests/`,
- name files `test_*.py`,
- prefer behavior-focused tests for MCP interaction boundaries and message formatting.

If a test framework is introduced, document the exact command in `README.md` and keep it runnable via `uv run ...`.

## Commit & Pull Request Guidelines
Git history is minimal (`init commit`, short imperative messages). Follow a clear imperative style, e.g., `Fix image persistence path for Chainlit`.

For pull requests, include:
- what changed and why,
- how to run/verify locally (commands),
- UI screenshots when chat output or rendering changes,
- notes for any `.env` or config updates.

Never commit real API keys or secrets.
