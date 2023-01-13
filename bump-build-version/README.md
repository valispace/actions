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

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
