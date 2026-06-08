# Python conventions

- Always write Python code following Black formatting conventions.
- Organize imports with standard library first, then third-party, then local (isort convention). Separate each section with newlines. Within each section, sort imports alphabetically.
- Type-annotate all parameters, return types, and stored instance attributes.
- Use uv for package and environment management.
- Use Pydantic models for structured data that crosses module, API, persistence, or validation boundaries. Plain dicts are acceptable for small local transformations. Each model class must live in its own file.
- Organize class methods in this order: `__init__` first, then other dunder methods (e.g. `__str__`, `__repr__`) sorted alphabetically, then public methods sorted alphabetically, then private methods (prefixed with `_` or `__`) sorted alphabetically.
- Prefer private methods for helpers that depend on class state. Use module-level private functions for stateless helpers used only within the module.
- [CRITICAL] Never read, load, parse, print, inspect, or otherwise access project `.env` files or values. Do not use `.env` files for verification, scripts, debugging, or local command setup.
- [CRITICAL] Never write or run one-off Python scripts that connect directly to project databases.
