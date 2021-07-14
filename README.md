# Python Wraptor example project using Poetry

Build Python projects without installing any build tools.

This fork of [Facebook's PathPicker](https://github.com/facebook/PathPicker) is augmented with
[Python Wraptor](https://github.com/houbie/python-wraptor) to show how you can build Python
projects without the hassle of maintaining multiple (versions of) build tools.

To try it out:
```shell
# make sure you have python > 3.6 on your path
python --version 
git clone https://github.com/houbie/PathPicker.git
cd PathPicker
./pw poetry install
./pw test
```

**NOTE** Building the project this way should also work on Windows,
although PathPicker itself is not intended for Windows.

## How?
Just by copying _pw_ and _pw.bat_ from [Python Wraptor](https://github.com/houbie/python-wraptor)
to your project's root and adding the **tool.wraptor** sections to _pyproject.toml_

```toml
[tool.wraptor]
poetry = "poetry==1.1.7"

[tool.wraptor.alias]
# convenience shortcut
run = "poetry run"
test = "poetry run pytest src/tests/"
```
