# Deploy

An opinionated convenience wrapper action for applications to deploy to AWS ECS or Fly.io

## Quickstart

```
  jobs:
    deploy:
      uses: opengovsg/deploy@latest
    secrets:
      # Set AWS secrets if you want to deploy to AWS
      aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}
      aws-role-arn: ${{ secrets.AWS_ROLE_ARN }}
      aws-region: ${{ secrets.AWS_REGION }}
      aws-ecr-repo: ${{ secrets.ECR_REPO }}
      # Set Fly.io secrets if you want to deploy to AWS
      fly-org-name: ${{ secrets.ORG_NAME }}
      fly-app-name: ${{ secrets.APP_NAME }}
      fly-api-token: ${{ secrets.FLY_API_TOKEN }}
    with:
      image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```