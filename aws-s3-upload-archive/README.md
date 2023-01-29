# Valispace aws-s3-upload-archive Action

This action uploads the given archive to the [Valispace](https://github.com/valispace) AWS S3 bucket.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/aws-s3-upload-archive@master
with:
  # Path to the archive to upload.
  # Required: true
  # Default: ''
  archive: 'valispace.tar.gz'
  # The AWS Secret Access Key.
  # Required: true
  # Default: ''
  aws-secret-access-key: '${{ secrets.AWS_SECRET_ACCESS_KEY }}'
  # The AWS Access Key ID.
  # Required: true
  # Default: ''
  aws-access-key-id: '${{ secrets.AWS_ACCESS_KEY_ID }}'
  # The AWS Region (e.g. `eu-central-1`).
  # Required: false
  # Default: 'eu-central-1'
  aws-region: 'eu-central-1'
  # The AWS S3 bucket where to upload.
  # Required: true
  # Default: ''
  aws-s3-bucket: '${{ secrets.S3_BUCKET }}'
  # The AWS S3 bucket repository (the name is case insensitive) where to upload.
  # Required: true
  # Default: ''
  aws-s3-repository: 'valispace'
  # The AWS S3 bucket branch where to upload.
  # Required: true
  # Default: ''
  aws-s3-branch: 'develop'
  # The AWS S3 bucket tag where to upload.
  # Required: false
  # Default: 'latest'
  aws-s3-tag: '1.0.0'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
