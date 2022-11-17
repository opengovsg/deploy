# Deploy

An opinionated convenience wrapper action for applications to deploy to AWS ECS

## Quickstart

```
jobs:
  deploy:
    runs-on: ubuntu-latest
    concurrency:
      group: ${{ github.ref }}
      cancel-in-progress: true
    permissions:
      # id-token scope granted to GitHub token used to run this job,
      # to facilitate deploys to AWS via OIDC
      id-token: write
      contents: read
    steps:
      - uses: opengovsg/deploy/aws@latest
        with:
          # Set AWS secrets to deploy to AWS
          aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}
          aws-role-arn: ${{ secrets.AWS_ROLE_ARN }}
          aws-region: ${{ secrets.AWS_REGION }}
          aws-ecr-repo: ${{ secrets.ECR_REPO }}
          # Specify an image tag that identifies the build
          image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```
