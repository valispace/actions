# Valispace build-archive Action

This action creates a compressed tarball (`tar.gz`) from the given directory.

**NOTE**

Patterns in `${{ inputs.directory }}/.exclude` will be used to exclude files and directories from the compressed tarball.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/build-archive@master
with:
  # Path to the directory to archive.
  # Required: true
  # Default: ''
  directory: 'backend'
  # The compressed tarball name.
  # Required: true
  # Default: ''
  archive-name: 'valispace-backend.tar.gz'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
