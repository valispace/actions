# Valispace bump-build-version Action

Given a project versioning file, this action bumps the build version according to the [Valispace Versioning Specification](https://valispace.atlassian.net/wiki/spaces/~62b97f79c9f2df7b608a092f/pages/2083324008/Valispace+Versioning+Specification) ( `major.minor.patch(-(alpha|release-candidate)-(epoch))?` ).

_The versioning file must contain a line with keyword `version` (e.g. "`version = 1.0.0`") for this action to succeed!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/bump-build-version@master
with:
  # Path to the versioning file.
  # Required: true
  # Default: ''
  versioning-file: 'backend/vali/__init__.py'
  # Update major version?
  # Required: false
  # Default: false
  update-major-version: false
  # Update minor version?
  # Required: false
  # Default: false
  update-minor-version: false
  # Update patch version?
  # Required: false
  # Default: false
  update-patch-version: false
  # Pre-release metadata (only 'alpha-epoch', 'release-candidate-epoch' or '' are allowed).
  # Required: false
  # Default: 'NaN'
  pre-release-metadata: 'release-candidate-1692107243'
```
<!-- end usage -->

## Outputs

### `release`

**release** output contains the new release version (e.g. 'x.y').

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/bump-build-version@master
        id: 'versioning'
        with:
          versioning-file: '__init__.py'
      - run: 'echo "RELEASE : ${{ steps.versioning.outputs.release }}"'
```

### `version`

**version** output contains the new build version (e.g. 'x.y.z(-(alpha|release-candidate)-(epoch))?').

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/bump-build-version@master
        id: 'versioning'
        with:
          versioning-file: '__init__.py'
      - run: 'echo "VERSION : ${{ steps.versioning.outputs.version }}"'
```

### `pre-release-type`

**version** output contains the new pre-release type (if defined) (e.g. 'alpha', 'release-candidate', '').

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/bump-build-version@master
        id: 'versioning'
        with:
          versioning-file: '__init__.py'
      - run: 'echo "PRE-RELEASE TYPE: ${{ steps.versioning.outputs.pre-release-type }}"'
```

### `pre-release-metadata`

**version** output contains the new pre-release metadata (if defined) (e.g. 'alpha-1692107243', 'release-candidate-1692112160', '').

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/bump-build-version@master
        id: 'versioning'
        with:
          versioning-file: '__init__.py'
      - run: 'echo "PRE-RELEASE METADATA : ${{ steps.versioning.outputs.pre-release-metadata }}"'
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
