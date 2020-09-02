# Usage

make sure:
1. `bump2version` is installed
2. your `.bumpversion.cfg` is set
3. `git-flow-avh` is installed
4. replace `<package>`with your package name

#### .bumpversion.cfg

```shell
[bumpversion]
current_version = 0.7
parse = (?P<major>\d+)(\.(?P<minor>.*))?
commit = True
tag = False
serialize = 
	{major}.{minor}

[bumpversion:file:<package>/__init__.py]
```

#### __init__.py

```python
__version__ = "0.1"
```

#### setup.py

```python

PACKAGE = "<package>"
pkg = __import__(PACKAGE)
VERSION = pkg.__version__

setuptools.setup(
    name=pkg.NAME,
    version=VERSION,

)
```