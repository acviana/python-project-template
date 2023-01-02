black:
	black {{cookiecutter.module_variable_name}}
	black tests

black-diff:
	black {{cookiecutter.module_variable_name}} --diff
	black tests --diff

export:
	poetry export -f requirements.txt -o requirements.txt
	poetry export -f requirements.txt -o requirements_dev.txt --with=dev

install:
	poetry install

mypy:
	mypy {{cookiecutter.module_variable_name}}/ --ignore-missing-imports

pre-commit: black mypy ruff test

ruff:
	ruff {{cookiecutter.module_variable_name}}/ tests/

test:
	pytest -vvs --cov-report term-missing --cov={{cookiecutter.module_variable_name}} tests/

_update:
	poetry update

update: _update export pre-commit

update-diff:
	poetry update --dry-run | grep -i updat
