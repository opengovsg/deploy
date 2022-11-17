# Deploy

An opinionated convenience wrapper action for applications to deploy to AWS ECS

## Quickstart

```
  jobs:
    deploy:
      uses: opengovsg/deploy/aws@latest
    secrets:
      aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}
      aws-role-arn: ${{ secrets.AWS_ROLE_ARN }}
      aws-region: ${{ secrets.AWS_REGION }}
      aws-ecr-repo: ${{ secrets.ECR_REPO }}
    with:
      image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```