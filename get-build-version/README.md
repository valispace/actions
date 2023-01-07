# Valispace get-build-version Action

Given a project versioning file, this action extracts the current release version, build version, pre-release type (if defined) and build metadata (if defined).

_The versioning file must contain a line with keyword `version` (e.g. "`version = 1.0.0`") for this action to return a valid output!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/get-build-version@master
with:
  # Path to the versioning file.
  # Required: true
  # Default: ''
  file: '__init__.py'
```
<!-- end usage -->

## Outputs

### `release`

**release** output contains the current release version (e.g. X.Y).

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

**version** output contains the current build version (e.g. X.Y.Z(-(alpha|release-candidate)+(YYYYMMDDHHMMSS))?).

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

### `pre-release`

**version** output contains the current pre-release type (if defined) (e.g. 'alpha', 'release-candidate').

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
      - run: 'echo "PRE-RELEASE : ${{ steps.versioning.outputs.pre-release }}"'
```

### `build-metadata`

**version** output contains the current build metadata (if defined) (e.g. YYYYMMDDHHMMSS).

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
      - run: 'echo "BUILD-METADATA : ${{ steps.versioning.outputs.build-metadata }}"'
```

## Versioning

[Valispace](https://github.com/valispace) follows the Semantic Versioning Specification (SemVer) defined at [Semantic Versioning.org](https://semver.org/), adapted for our own context.

In short, we name our versions as `major.minor.patch(-(alpha|release-candidate)+(YYYYMMDDHHMMSS))?`.

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
