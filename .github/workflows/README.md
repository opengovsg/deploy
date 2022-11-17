# Fly.io Deploy

An opinionated convenience wrapper action for applications to deploy

## Quickstart

```
  jobs:
    deploy:
      uses: opengovsg/deploy/.github/workflows/fly.yml@latest
    secrets:
      fly-org-name: ${{ secrets.ORG_NAME }}
      fly-app-name: ${{ secrets.APP_NAME }}
      fly-api-token: ${{ secrets.FLY_API_TOKEN }}
    with:
      image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}


```

```
  jobs:
    deploy:
      uses: opengovsg/deploy/.github/workflows/aws.yml@latest
    secrets:
      aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}
      aws-role-arn: ${{ secrets.AWS_ROLE_ARN }}
      aws-region: ${{ secrets.AWS_REGION }}
      aws-ecr-repo: ${{ secrets.ECR_REPO }}
    with:
      image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}      
      ecs-cluster-name: 'cluster-application-server'
      ecs-service-name: 'application-server'
      ecs-container-name: 'app-server'
      codedeploy-application: 'AppECS-cluster-application-server'
      codedeploy-deployment-group: 'DgpECS-cluster-application-server'
```
