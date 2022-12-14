# Valispace bump-build-version Action

Given a project versioning file, this action bumps the build version according to the [Valispace Versioning Specification](https://valispace.atlassian.net/wiki/spaces/~62b97f79c9f2df7b608a092f/pages/2083324008/Valispace+Versioning+Specification) ( `major.minor.patch(-(alpha|release-candidate)-(epoch))?` ).

_The versioning file must contain a line with keyword `version` (e.g. "`version = 1.0.0`") for this action to succeed!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/bump-build-version@master
with:
  # Update major version?
  # Required: false
  # Default: false
  major: false
  # Update minor version?
  # Required: false
  # Default: false
  minor: false
  # Update patch version?
  # Required: false
  # Default: false
  patch: false
  # Pre-release metadata ( accepts: 'alpha-epoch', 'release-candidate-epoch', '').
  # Required: false
  # Default: 'NaN'
  pre-release: 'release-candidate-1692107243'
  # Path to the versioning file.
  # Required: true
  # Default: ''
  file: '__init__.py'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
