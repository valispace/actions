# Valispace setup-python Action

This action extends [actions/setup-python](https://github.com/actions/setup-python) by installing packages `pkg-config`, `xmlsec1`, `libxmlsec1`, `libxmlsec1-dev` and the given list of python requirements (optionally).

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/setup-python@master
with:
  # Version range or exact version of Python to use, using SemVer's version range syntax.
  # Required: false
  # Default: '3.9'
  python-version: '3.9'
  # Path to the python requirements file.
  # Required: false
  # Default: 'requirements.txt'
  python-requirements-file: 'requirements.txt'
  # Whether to install required packages and python requirements after setup.
  # Required: false
  # Default: true
  python-install-requirements: true
env:
  GITHUB_TOKEN: '${{ secrets.GITHUB_TOKEN }}'
```
<!-- end usage -->

## Outputs

### `python-version`

Using **python-version** output it's possible to get the installed by action Python version. This output is useful when the input `python-version` is given as a range (e.g. 3.8.0 - 3.10.0 ), but down in a workflow you need to operate with the exact installed version (e.g. 3.10.1). 

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/setup-python@master
        id: 'cp310'
        with:
          python-version: '3.8.0 - 3.10.0'
      - run: 'echo "${{ steps.cp310.outputs.python-version }}"'
```

### `python-path`

**python-path** output is available with the absolute path of the Python interpreter executable if you need it:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/setup-python@master
        id: 'cp310'
        with:
          python-version: '3.10'
      - run: 'pipx run --python "${{ steps.cp310.outputs.python-path }}" nox --version'
```

### `cache-hit`

**cache-hit** output is available with a boolean value that indicates whether a cache hit occurred on the primary key:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/setup-python@master
        id: 'cp310'
        with:
          python-version: '3.8.0'
          python-requirements-file: 'requirements.txt'
          python-install-requirements: true
      - run: 'echo "${{ steps.cp310.outputs.cache-hit }}"' # true if cache-hit occurred on the primary key
```

## Environment variables

These environment variables become available after setup-python action execution:

| **Env.variable**    | **Description**                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------- |
| pythonLocation      |Contains the absolute path to the folder where the requested version of Python is installed|
| Python_ROOT_DIR     |https://cmake.org/cmake/help/latest/module/FindPython.html#module:FindPython               |
| Python2_ROOT_DIR    |https://cmake.org/cmake/help/latest/module/FindPython2.html#module:FindPython2             |
| Python3_ROOT_DIR    |https://cmake.org/cmake/help/latest/module/FindPython2.html#module:FindPython3             |

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
