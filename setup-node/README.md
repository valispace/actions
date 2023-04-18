# Valispace setup-node Action

This action extends [actions/setup-node](https://github.com/actions/setup-node) by installing the given list of Node.js dependencies (optionally) in one step.

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/setup-node@master
with:
  # Version range or exact version of Node.js to use, using SemVer's version range syntax.
  # Required: false
  # Default: '18'
  node-version: '18'
  # Path to the Node.js dependencies file.
  # Required: false
  # Default: ''
  node-dependencies-file: 'package-lock.json'
  # Whether to install required Node.js dependencies after setup.
  # Required: false
  # Default: 'false'
  node-install-dependencies: true
```
<!-- end usage -->

## Outputs

### `node-version`

Using **node-version** output it's possible to get the installed by action Node.js version. This output is useful when the input `node-version` is given as a range (e.g. `18.x` ), but down in a workflow you need to operate with the exact installed version (e.g. `18.4.0`). 

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/setup-node@master
        id: 'cp18'
        with:
          node-version: '18.x'
      - run: 'echo "${{ steps.cp18.outputs.node-version }}"'
```

### `cache-hit`

The **cache-hit** output contains a boolean value that indicates whether a cache hit occurred on the primary key:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: valispace/actions/setup-node@master
        id: 'cp18'
        with:
          node-version: '18.4.0'
          node-dependencies-file: 'package-lock.json'
          node-install-dependencies: true
      - run: 'echo "${{ steps.cp310.outputs.cache-hit }}"' # true if cache-hit occurred on the primary key
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
