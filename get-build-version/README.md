# Valispace get-build-version Action

Given a project versioning file, this action extracts the current project release version (`release`) and build version (`version`).

The versioning file must contain a line with keyword `version` (e.g. "`version = 1.0.0`") for this action to return a valid output.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/get-build-version@master
with:
    # Path to the versioning file.
    # Default: ''
    file: '__init__.py'
```
<!-- end usage -->

## Outputs

### `release`

**release** output contains the current project release version (e.g. XX.YY).

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/get-build-version@master
      id: 'versioning'
      with:
        file: '__init__.py'
    - run: 'echo "RELEASE : ${{ steps.versioning.outputs.release }}"'
```

### `version`

**version** output contains the current project version (e.g. XX.YY.ZZ).

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/get-build-version@master
      id: 'versioning'
      with:
        file: '__init__.py'
    - run: 'echo "VERSION : ${{ steps.versioning.outputs.version }}"'
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
