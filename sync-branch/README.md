# Valispace sync-branch action

This action creates a branch, merges specific files from the source branch, and opens a PR with the target branch.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/sync-branch@master
with:
  # Github Token
  # Required: true
  # Default: ''
  github-token: '${{ secrets.GITHUB_TOKEN }}'
  # The name of the branch where the PR will merge to
  # Required: true
  # Default: ''
  to-branch: 'main'
  # The name of the branch to be created
  # Required: true
  # Default: ''
  temp-branch: 'temp-branch'
  # The id of the PR Autor
  # Required: false
  # Default: ''
  pr-author-id: '1234'
  # List of files to be merged from the source branch
  # Required: true
  # Default: ''
  files: 'file1,file2'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
