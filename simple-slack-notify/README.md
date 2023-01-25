# Valispace simple-slack-notify Action

This is a fork from [adamkdean/simple-slack-notify](https://github.com/adamkdean/simple-slack-notify), _which is no longer maintained_, in order to update the action to Node16.

## Usage

<!-- start usage -->
```yaml
uses: valispace/actions/simple-slack-notify@master
with:
  # Unique URL to where the JSON payload with the message should be sent.
  # Required: true
  # Default: ''
  webhook: '${{ secrets.SLACK_WEBHOOK_URL }}'
  # The channel you want to send to, such as '#general'.
  # Required: false
  # Default: ''
  channel: '#general'
  # Disable JS evaluation of strings.
  # Required: false
  # Default: ''
  disable_eval: 'true'
  # Used to override the default username.
  # Required: false
  # Default: ''
  username: 'valispace'
  # The color you want to use (can be 'good', 'danger', 'warning' or a hex code).
  # Required: false
  # Default: ''
  color: 'good'
  # Pass the job status through and omit color for status based color.
  # Required: false
  # Default: ''
  status: 'success'
  # The message that you want to send regardless of status.
  # Required: false
  # Default: ''
  text: 'A message from GitHub Actions.'
  # The message to send if status is 'success'.
  # Required: false
  # Default: ''
  success_text: 'Success!'
  # The message to send if status is 'failure'.
  # Required: false
  # Default: ''
  failure_text: 'Failure!'
  # The message to send if status is 'cancelled'.
  # Required: false
  # Default: ''
  cancelled_text: 'Cancelled!'
  # JSON string containing an array of fields to attach to the notification.
  # Required: false
  # Default: '[]'
  fields: '[]'
```
<!-- end usage -->

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
