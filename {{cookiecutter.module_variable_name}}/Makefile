black:
	black {{cookiecutter.module_variable_name}}
	black tests

black-diff:
	black {{cookiecutter.module_variable_name}} --diff
	black tests --diff

export:
	poetry export -f requirements.txt -o requirements.txt
	poetry export -f requirements.txt -o requirements_dev.txt --with=dev

flake8:
	flake8 {{cookiecutter.module_variable_name}}/ tests/ --statistics

install:
	poetry install

pre-commit: black flake8 test

test:
	pytest -vvs --cov-report term-missing --cov={{cookiecutter.module_variable_name}} tests/

_update:
	poetry update

update: _update export pre-commit

update-diff:
	poetry update --dry-run | grep -i updat
