# common-workflows
Workflows used in different repositories

## Build multi-arch docker images (amd64/arm64) on AWS spot instances

Example:

```
name: Build multi-arch docker image

on: [workflow_dispatch]

jobs:
  build:
    name: Build
    uses: pldin601/common-workflows/.github/workflows/build-multiarch-on-aws-spots.yml@setup-spots
    with:
      DOCKER_IMAGE_TAG: latest
    secrets:
      AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
      AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      DOCKERHUB_USERNAME: ${{ secrets.DOCKERHUB_USERNAME }}
      DOCKERHUB_TOKEN: ${{ secrets.DOCKERHUB_TOKEN }}
```
