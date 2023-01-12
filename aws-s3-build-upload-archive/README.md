# Valispace aws-s3-build-upload-archive Action

This action builds a tarball archive of the given application and uploads it to the [Valispace](https://github.com/valispace) AWS S3 bucket.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/aws-s3-build-upload-archive@master
with:
  # Application to archive and upload (optional) (e.g. 'backend').
  # Required: true
  # Default: ''
  application: 'backend'
  # Archive name of the application (must include 'tar.gz' extension).
  # Required: true
  # Default: 'archive.tar.gz'
  archive: 'valiengine.tar.gz'
  # Upload archive to AWS S3 bucket.
  # Required: false
  # Default: 'false'
  upload: true
  # AWS Secret Access Key.
  # Required: true
  # Default: ''
  aws-secret-access-key: '${{ secrets.AWS_SECRET_ACCESS_KEY }}'
  # AWS Access Key ID.
  # Required: true
  # Default: ''
  aws-access-key-id: '${{ secrets.AWS_ACCESS_KEY_ID }}'
  # AWS Region (e.g. 'eu-central-1').
  # Required: false
  # Default: 'eu-central-1'
  aws-region: 'eu-central-1'
  # The AWS S3 bucket where to upload.
  # Required: false
  # Default: ''
  aws-s3-bucket: '${{ secrets.S3_BUCKET }}'
  # The AWS S3 bucket repository (the name is case insensitive) where to upload.
  # Required: false
  # Default: ''
  aws-s3-repository: 'valiengine'
  # The AWS S3 bucket branch where to upload.
  # Required: false
  # Default: ''
  aws-s3-branch: 'develop'
  # The AWS S3 bucket tag where to upload.
  # Required: false
  # Default: 'latest'
  aws-s3-tag: '1.38.1-alpha-1692107243'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
