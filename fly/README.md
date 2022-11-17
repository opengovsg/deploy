# Fly.io Deploy

An opinionated convenience wrapper action for applications to deploy to Fly.io

## Quickstart

```
jobs:
  deploy:
    runs-on: ubuntu-latest
    concurrency:
      group: ${{ github.ref }}
      cancel-in-progress: true
    steps:
      - uses: opengovsg/deploy/fly@latest
        with:
          # Set Fly.io secrets to deploy to Fly.io
          fly-org-name: ${{ secrets.ORG_NAME }}
          fly-app-name: ${{ secrets.APP_NAME }}
          fly-api-token: ${{ secrets.FLY_API_TOKEN }}
          # Specify an image tag that identifies the build
          image-tag: ghactions-${{ github.ref_name }}-${{ github.sha }}
```
