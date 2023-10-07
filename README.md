# Python Template 🐍
A template repo holding common setup for a python project.

## Installation

You can install the package using pip

```bash
pip install -e .
```

or for development

```bash
pip install -e ".[dev]"
```

## Structure

The project has the following structure

```
├── .gitignore
├── Makefile
├── README.md
├── setup.py
├── src
│   ├── __init__.py 
│   ├── hello.py 
└── test 
    └── test_hello.py
```

### Code Quality 🧹

Two handy commands inside the `Makefile` are provided, namely:

- `make style` to format the code
- `make check_code_quality` to check code quality (PEP8 basically)

So far, **there is no types checking with mypy**. See [issue](https://github.com/roboflow-ai/template-python/issues/4). 

### Tests 🧪

[`pytests`](https://docs.pytest.org/en/7.1.x/) is used to run our tests.

### Publish on PyPi 🚀

**Important**: Before publishing, edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.

Use [`twine`](https://twine.readthedocs.io/en/stable/) to make your life easier. You can publish by using

```
export PYPI_USERNAME="you_username"
export PYPI_PASSWORD="your_password"
export PYPI_TEST_PASSWORD="your_password_for_test_pypi"
make publish -e PYPI_USERNAME=$PYPI_USERNAME -e PYPI_PASSWORD=$PYPI_PASSWORD -e PYPI_TEST_PASSWORD=$PYPI_TEST_PASSWORD
```

You can also use token for auth, see [pypi doc](https://pypi.org/help/#apitoken). In that case,

```
export PYPI_USERNAME="__token__"
export PYPI_PASSWORD="your_token"
export PYPI_TEST_PASSWORD="your_token_for_test_pypi"
make publish -e PYPI_USERNAME=$PYPI_USERNAME -e PYPI_PASSWORD=$PYPI_PASSWORD -e PYPI_TEST_PASSWORD=$PYPI_TEST_PASSWORD
```

**Note**: Thanks to the Roboflow supervision team for this beautiful, short and sweet Python project setup.

The **correct steps** to create a new realease are the following:
- edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.