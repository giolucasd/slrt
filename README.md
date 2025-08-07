# Sign Language Recognition and Translation <!-- omit from toc -->

This repo contains ongoing work on sign language recognition and translation.

This code is based on the amazing [SignJoey](https://github.com/neccam/slt) that introduced joint continuous sign language recognition and translation.

- [1. Setup](#1-setup)
- [2. Usage](#2-usage)
- [3. Development Tools](#3-development-tools)
  - [Linting \& Formatting](#linting--formatting)
  - [Testing](#testing)
  - [Test Coverage](#test-coverage)

## 1. Setup

* Download the feature files using the `data/download.sh` script.

* Create a python virtual environment and activate it. We **strongly** recommend using [uv](https://docs.astral.sh/uv/).
```bash
uv venv --python 3.12
source .venv/bin/activate
```

* Install required packages:
```bash
uv sync
```

## 2. Usage
```bash
uv run signjoey train configs/sign.yaml
``` 

> Note that the default data directory is `./data`. If you download them to somewhere else, you need to update the `data_path` parameters in your config file.

## 3. Development Tools

### Linting & Formatting

We use [ruff](https://docs.astral.sh/ruff/) for linting and formatting. To check and fix code style:

```bash
uv run ruff check signjoey/
uv run ruff format signjoey/
```

Or run both with pre-commit hooks:

```bash
uv run pre-commit run --all-files
```

### Testing

We use [pytest](https://docs.pytest.org/) for running tests:

```bash
uv run pytest
```

### Test Coverage

To check test coverage, use [coverage.py](https://coverage.readthedocs.io/):

```bash
uv run coverage run -m pytest
uv run coverage report
uv run coverage html
```

---
