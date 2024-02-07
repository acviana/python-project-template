## Python Project Cookiecutter Template

This is a hand-rolled cookiecutter template for Python projects.
It's build around best-practices originally influenced by the [Hypermodern Python](https://cjolowicz.github.io/posts/hypermodern-python-01-setup/) series of articles.

### Technologies

This template comes bundled with the following technologies:

 - Python version management with [pyenv](https://github.com/pyenv/pyenv)
 - Dependency management with [Poetry](https://python-poetry.org/)
 - Testing with [pytest](https://docs.pytest.org/en/6.2.x/)
 - Linting with [ruff](https://github.com/charliermarsh/ruff)
 - Type checking with [mypy](https://mypy-lang.org/)
 - Docstring-driven documentation with [Sphinx](https://www.sphinx-doc.org/en/master/) and the [Autodoc](https://www.sphinx-doc.org/en/master/usage/extensions/autodoc.html#module-sphinx.ext.autodoc) extension.
 - Suggested usage patterns are documented in the project Makefile

The template will include all of these technologies out-of-the-box, but you can easily remove anything that's not needed for a particular project.

#### Deprecated Technologies

As I've started migrating to Ruff as a linter and formatter I've rolled off of Black and Flake8 as daily drivers - but both still great projects!

### Usage

First install the [cookiecutter](https://cookiecutter.readthedocs.io/) project. You can then build a template project:

```bash
$ cookiecutter https://github.com/acviana/python-project-template.git
```

### Development

Developing a cookiecutter template can be difficult because you have to continuously build the project to test your implementation.
To help with develop/build/test loop I created another [project](https://github.com/acviana/python-project-template-testing) with a script to download and run python projects from any branch in this repo.
