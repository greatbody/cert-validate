# Cert Validate

A tool library that helps you get the validate date of a domain's certification.

**note** This package is at active development, and early stage release is not recommended for production use.

# Usage

```bash
python3 -m pip install cert-validate
```

Create a test.py file
```python3
from cert_validate import cert_validate
cert_validate.cert_validate_date("www.google.com")
```

```bash
python3 -m test
```

Output

```
SSL version: TLSv1.3
Expire time: Jan 24 03:19:35 2022 GMT
2022-01-24 03:19:35+00:00
2022-01-24 11:19:35 +0800
```

# Development
## Development dependence tools

> Tool you need to build package

```bash
python3 -m pip install setuptools
```

> Tool you need to publish your package to PyPI

```bash
python3 -m pip install --upgrade twine
```

## Build the package

Run this command at the root folder of this project.

```bash
python3 -m build
```

## Development accounts

You will need account in PyPI to publish your packages.

> Registe a test account for your test use

You definitely would like to avoid situation where your first published version is not usable, use this test PyPI is a good way.

https://test.pypi.org/account/register/

> Registe a offical PyPI account

When it comes to the time when you need to offically release your package, you will need an PyPI account.

https://pypi.org/account/register/

## Create token of testpypi to publish your package

Goto https://test.pypi.org/manage/account/token/ generate a token

Create a $HOME/.pypirc file with this content

```
[testpypi]
username = __token__
password = [token generated]
```

## Publish your package to test

```bash
python3 -m twine upload --repository testpypi dist/*
```

## Create token of pypi to publish your package for publish release

Goto https://pypi.org/manage/account/token/ generate a token

Create/Insert into $HOME/.pypirc file with this content

```
[pypi]
username = __token__
password = [token generated]
```

## Publish your package to public

```bash
python3 -m twine upload dist/*
```
