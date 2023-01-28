# Valispace get-build-version Action

Given a project versioning file, this action extracts the current release version, build version, pre-release type (if defined) and pre-release metadata (if defined), as defined in the [Valispace Versioning Specification](https://valispace.atlassian.net/wiki/spaces/~62b97f79c9f2df7b608a092f/pages/2083324008/Valispace+Versioning+Specification) ( `major.minor.patch(-(alpha|release-candidate)-(<epoch>))?` ).

_The versioning file must contain a line with keyword `version` (e.g. "`version = 1.0.0`") for this action to return a valid output!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/get-build-version@master
with:
  # Path to the versioning file.
  # Required: true
  # Default: ''
  versioning-file: 'backend/vali/__init__.py'
```
<!-- end usage -->

## Outputs

The following outputs are available:
|Name|Type|Description|
|---|---|---|
|release|String|The current release version (e.g. '1.0')|
|version|String|The current build version (e.g. '1.0.0-release-candidate-1692107243')|
|pre-release-type|String|The current pre-release type (if defined) (e.g. 'release-candidate')|
|pre-release-metadata|String|The current pre-release metadata (if defined) (e.g. 'release-candidate-1692107243')|

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
