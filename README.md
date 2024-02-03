# setup-aws-cli

Action to install and configure AWS CLI.

This action enables you to run AWS CLI commands as part of your workflow.

## Example

```yaml
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: sumanshu-nankana/setup-aws-cli
        with:
          region: 'eu-west-1'
          access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          secret-access-key: ${{ secrets. AWS_SECRET_ACCESS_KEY }}
          aws-cli-version: 1.32.33
          output-format: json
      # Run AWS Commands
      - run: aws s3api list-buckets
```

## Inputs

### `region`

Required Input
The AWS Region to configure and run your aws commands.

### `access-key-id`

Required Input
The AWS Access KEY ID to access AWS account

### `secret-access-key`

Required Input
The AWS Secret Access KEY to access AWS account

### `aws-cli-version`

Optional Input
If you want to install any specific version of [awscli](https://pypi.org/project/awscli/), else default it will pick whatever latest version is available 


### `output-format`

Optional Input
The Output format of AWS commands


You can use [`sumanshu-nankana/setup-aws-cli`](https://github.com/Sumanshu-Nankana/setup-aws-cli) to automatically set up AWS CLI.
