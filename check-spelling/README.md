# Valispace check-spelling Action

This action extends [check-spelling/check-spelling](https://github.com/check-spelling/check-spelling) by simplifying the inputs and outputs, while also providing a set of words valid in the [Valispace](https://www.valispace.com/) software context.

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/check-spelling@master
with:
  # Try to treat a GitHub event "a" as GitHub event "b" (JSON map).
  # Required: false
  # Default: ''
  event_aliases: '{"schedule":"push"}'
  # If set, only check files changed since the last push.
  # Required: false
  # Default: '1'
  only_check_changed_files: '1'
```
<!-- end usage -->

## Outputs

### `unknown_words`

Using **unknown_words** output it's possible to get the unrecognized words, that should be added to `expect.txt` file.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.unknown_words }}"'
```

### `stale_words`

Using **stale_words** output it's possible to get the stale words, that should be removed from `expect.txt` file.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.stale_words }}"'
```

### `skipped_files`

Using **skipped_files** output it's possible to get the skipped files, that should be added to `excludes.txt` file.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.skipped_files }}"'
```

### `suggested_dictionaries`

Using **suggested_dictionaries** output it's possible to get the suggested dictionaries, that can be added to `extra_dictionaries` input.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.suggested_dictionaries }}"'
```

### `warnings`

Using **warnings** output it's possible to get the list of warnings.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.warnings }}"'
```

### `result_code`

The **result_code** output indicates whether unrecognized words were found or comment needs to be collapsed.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - run: 'echo "${{ steps.spelling.outputs.result_code }}"'
```

### `followup`

The **followup** output indicates whether the workflow should do a follow up action.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: valispace/actions/check-spelling@master
      id: 'spelling'
    - if: ${{ steps.spelling.outputs.followup }}
      uses: valispace/actions/setup-python@master
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
