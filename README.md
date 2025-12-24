# permalint

[![Release](https://github.com/sanchitram1/permalint/actions/workflows/release.yml/badge.svg)
](https://github.com/sanchitram1/permalint/actions/workflows/release.yml)
[![Coverage Status](https://coveralls.io/repos/github/sanchitram1/permalint/badge.svg?branch=config)
](https://coveralls.io/github/sanchitram1/permalint?branch=config)

Lint URLs (mostly for teaxyz/chai, but hopefully other uses too)

## Features

- Ignores protocol (http, https, etc.)
- Normalizes GitHub URLs to owner/repo
- Removes query strings and fragments
- Lowercases domains and removes www

## Usage

```python
from permalint import normalize_url

url = "https://github.com/user/repo?utm_source=foo#readme"
print(normalize_url(url))  # Output: github.com/user/repo
```

## Development

- Install dependencies: `pkgx rye sync`
- Run tests: `uv run pytest`
- Lint: `uv run ruff check . && uv run ruff format .`
- Type check: `uv run ty check src/`

## Contributing / Wishlist

- `guess-canonical-url` to guess the correct URL based on a passed list of URLs
- actual source of Homepages for

## Tasks

### cov

Requires the COVERALLS_REPO_TOKEN to be set in a .env file

```bash
export $(grep -v '^#' .env | xargs)
uv run coveralls
```

### lint

```bash
uv run ruff check . --fix --unsafe-fixes
uv run format .
```