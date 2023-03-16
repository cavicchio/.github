# GitHub Workflow Templates

## Docker Build

Uses the project's Dockerfile to build the source into a Docker image, then push it to the GitHub Container Registry.

**Runs on:**
- *push* to any branch
- *pull request* to any branch

**Docker image tags:**
- `<Git commit hash>`
    - Since images are built for every commit, each built image can be uniquely tagged with the hash of the Git commit that triggered the build. Every built image will retain this tag. This is useful for deploying old versions when we aren't using semantic versioning.
- `<Git branch name>`
    - Every newly built image will be tagged with the branch that the image was built from. The branch tag will always point to the latest build from that branch.
- `latest`
    - The `latest` tag will be applied to the latest build from the default (typically master or main) branch. Since `latest` is used when pulling a Docker image without specifying a tag, pulling an image this way will get the latest stable build from the default branch.
