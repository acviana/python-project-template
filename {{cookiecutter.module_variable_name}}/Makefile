.PHONY: docs

check-outdated:
	poetry show --outdated

docs:
	(cd docs && make html)

export-requirements:
	poetry export -f requirements.txt -o requirements.txt
	poetry export -f requirements.txt -o requirements_dev.txt --with=dev

format:
	ruff format {{cookiecutter.module_variable_name}}
	ruff format tests

install:
	poetry install

mypy:
	mypy {{cookiecutter.module_variable_name}}/ --ignore-missing-imports

pre-commit: format mypy lint test

publish-release: pre-commit docs export-requirements

lint:
	ruff check {{cookiecutter.module_variable_name}}/ tests/

test:
	pytest -vvs --cov-report term-missing --cov={{cookiecutter.module_variable_name}} tests/

_update:
	poetry update

update-all: _update publish-release

update-all-diff:
	poetry update --dry-run | grep -i updat
