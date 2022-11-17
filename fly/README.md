# Fly.io Deploy

An opinionated convenience wrapper action for applications to deploy to Fly.io

## Quickstart

```
  jobs:
    deploy:
      uses: opengovsg/deploy/fly@latest
    secrets:
      fly-org-name: ${{ secrets.ORG_NAME }}
      fly-app-name: ${{ secrets.APP_NAME }}
      fly-api-token: ${{ secrets.FLY_API_TOKEN }}
    with:
      image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```
