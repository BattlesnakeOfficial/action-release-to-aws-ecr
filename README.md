# action-release-to-aws-ecr

A GitHub action to build docker images and push them to AWS ECR.

## Usage

```yaml
name: Release
on:
  release:
    types: [published]
    branches: [main]
jobs:
  release:
    name: Release
    runs-on: ubuntu-latest
    steps:
    - name: Release to AWS ECR
      uses: BattlesnakeOfficial/action-release-to-aws-ecr@main
      with:
        # Required
        aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws_region: ${{ secrets.AWS_REGION }}
        # Optional
        slack_webhook_url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
