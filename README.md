# Deploy

An opinionated convenience wrapper action for applications to deploy to AWS ECS or Fly.io

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
      - uses: opengovsg/deploy@latest
        with:
          # Set AWS secrets if you want to deploy to AWS
          aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}
          aws-role-arn: ${{ secrets.AWS_ROLE_ARN }}
          aws-region: ${{ secrets.AWS_REGION }}
          aws-ecr-repo: ${{ secrets.ECR_REPO }}
          # Set Fly.io secrets if you want to deploy to Fly.io
          fly-org-name: ${{ secrets.ORG_NAME }}
          fly-app-name: ${{ secrets.APP_NAME }}
          fly-api-token: ${{ secrets.FLY_API_TOKEN }}
          # Specify an image tag that identifies the build
          image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```
