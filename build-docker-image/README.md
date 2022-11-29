# Valispace build-docker-image Action

Builds the project docker image, based on the given `Dockerfile`.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/build-docker-image@master
with:
  # Name for the docker image.
  # Default: '${{ github.repository }}'
  name: 'valispace/engine'
  # Tag for the docker image.
  # Default: 'latest'
  tag: '1.0.0'
  # Path to the Dockerfile.
  # Default: 'Dockerfile'
  dockerfile: 'docker/Dockerfile'
  # Archive name of the docker image (must include 'tar.gz' extension).
  # Default: 'docker.tar.gz'
  archive: 'engine-docker.tar.gz'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
