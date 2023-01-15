# Valispace docker-build-image Action

This action extends [docker/build-push-action](https://github.com/docker/build-push-action) by focusing in just building a Docker image, while also simplifying the inputs and outputs.

_This is **not** intended to replace the original action!_

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/docker-build-image@master
with:
  # Build's context is the set of files located in the specified PATH or URL.
  # Required: false
  # Default: '.'
  context: '.'
  # Path to the Dockerfile.
  # Required: false
  # Default: 'Dockerfile'
  dockerfile: 'backend/vali/Dockerfile'
  # Docker image specification tarball name (e.g. `valispace-docker.tar.gz`).
  # Required: false
  # Default: ''
  archive-name: 'vali-docker-backend.tar.gz'
  # List of metadata for an image.
  # Required: false
  # Default: ''
  labels: |
    version=1.0.0
  # List of tags.
  # Required: false
  # Default: '${{ github.repository }}:latest'
  tags: |
    valispace/vali-backend:latest
    valispace/vali-backend:1.0.0
```
<!-- end usage -->

## Outputs

The following outputs are available:
|Name|Type|Description|
|---|---|---|
|image-id|String|Image ID|
|digest|String|Image digest|
|metadata|JSON|Build result metadata|

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
