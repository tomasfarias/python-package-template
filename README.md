# python-package-template

A template to kickstart a Python package with dependency and package management, static type checking, unit tests, code formatting, CI/CD (via GitHub Actions), and PEP8 style enforcement.

# Motivation

Everytime I start a new Python package I find myself running the same `poetry` commands, installing the usual development packages, and setting up a basic CI/CD pipeline. To speed up this process, I've created a package template that can be used as a starting point for my Python packages.

# Usage

Start off by cloning this repo into the directory you want for your new Python project:

```sh
git clone git@github.com:tomasfarias/python-package-template.git my-new-python-project
```

Now simply remove the existing `.git` folder and initialize a new repo:

```sh
cd my-new-python-project
rm -rf .git
git init .
```

Install development dependencies:

```sh
poetry install
```

Consider installing the `pre-commit` hooks:

```sh
poetry run pre-commit install
```

Make sure to update the package name, author, description, license, this README, and any other setting you consider relevant before making your first commit:

```sh
git add .
git commit -m "Initial commit"
```

# Dependencies

Let's go over the dependencies included in the template.

## Dependency management via poetry

This template comes with a `pyproject.toml` file that works perfectly with [`poetry`](https://python-poetry.org/). You can run `poetry install` right after cloning to get all development dependencies detailed below.

## Unit testing with pytest

[`pytest`](https://docs.pytest.org/en/latest/) is my testing framework of choice. The project template includes a `test/` directory with a placeholder test file and `conftest.py`. Write your unit tests in any `test_*.py` file and add your re-usable fixtures in `conftest.py`.

## Code formatting with black

[`black`](https://github.com/psf/black) has become the standard code formatter in all of my Python projects. The only settings included with the project specify some common directories and file patterns to ignore, and a max line length of 88. Max line length is usually a controversial topic, but I belive it comes down to personal preference, so edit this parameter at your discretion. Personally, I'm fine with anything between 80 and 110.

## Static type checking with mypy

I cannot ignore the benefits of static typing, even in its imperfect form when applied to code written in a dynamically (or "duck") typed language like Python. In particular, static typing makes reasoning about code much more easier as you make the type bounds you are working with explicit. And we all know that "Explicit is better than implicit".

[`mypy`](http://mypy-lang.org/) is simply the standard when it comes to static type checking.

## Linting with ruff

[`ruff`](https://github.com/charliermarsh/ruff) combines the functionality of [`flake8`](https://pypi.org/project/flake8/) (+ plugins), [`isort`](https://pypi.org/project/isort/), and other linters in a single tool with incredible performance.

## Check every commit with pre-commit

All these dependencies are great, but they still need to be manually run. That's where `git` hooks come in, and [`pre-commit`](https://pre-commit.com/) just makes managing `git` hooks a breeze.

# License

See ![LICENSE](LICENSE).
