# GitHub Actions DevOps Examples

[![Lint Code Base](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-super-linter.yaml/badge.svg)](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-super-linter.yaml)
[![Docker Build](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-docker-build.yaml/badge.svg)](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-docker-build.yaml)
[![Snyk Scan](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-snyk-scan-image.yaml/badge.svg)](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-snyk-scan-image.yaml)
[![Trivy Scan](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-trivy-scan-image.yaml/badge.svg)](https://github.com/BretFisher/github-actions-templates/actions/workflows/call-trivy-scan-image.yaml)

See this repositories [`.github`](.github) directory for examples on linters, workflows, and dependabot.

Reusable workflows are great. [`.github/workflows`](.github/workflows) stores three types of files:

- `reusable-*.yaml` - the workflow is designed to be reusable as a "called" workflow, and has a `workflow_call` event in it. They would exist in a central repository that is either `public` or `internal` and called by other repositories.
- `call-*.yaml` - this calls a reusable workflow that lives in other repositories or files with `uses: <github-path>`.
- `call-local*.yaml` - Same as above, but calls a local workflow in the same directory. This is typically used for testing. ProTip: Test your reusable workflows! Either in the same repository as this one shows, or from a separate repository full of tests.
- Any other workflows are just designed to run inside a repository directly.

## Examples

- [`.github/dependabot.yml`](.github/dependabot.yml) will make PRs for version updates to your Actions *and* Dockerfiles.
- [`.github/linters/`](.github/linters/) stores linter configs used by Super-Linter. ProTip: symlink these to the preferred location to use the same linters locally.
- [`.github/workflows/call-super-linter.yaml`](.github/workflows/call-super-linter.yaml) is a workflow that calls Super-Linter, which I'm storing the full reusable workflow in [bretfisher/super-linter-workflow](https://github.com/BretFisher/super-linter-workflow).
- [`.github/workflows/call-docker-build.yaml`](.github/workflows/call-docker-build.yaml) is a workflow that calls a Docker build (awesomesauce!), which I'm storing the full reusable workflow in [bretfisher/docker-build-workflow](bretfisher/docker-build-workflow).
- [`.github/workflows/call-docker-build-promotion.yaml`](.github/workflows/call-docker-build-promotion.yaml) is an advanced workflow that calls a build workflow on PR, and then on merge, it calls that workflow with different values and [also creates a GitOps-style PR](.gitub/workflows/reusable-gitops-pr.yaml) to deploy the new image to a Kubernetes cluster.
- [`.github/workflows/call-snyk-scan-image.yaml`](.github/workflows/call-snyk-scan-image.yaml) is a workflow that calls a [Snyk](https://github.com/snyk/cli) scan [in this repository](.github/workflows/reusable-snyk-scan-image.yaml).
- [`.github/workflows/call-trivy-scan-image.yaml`](.github/workflows/call-trivy-scan-image.yaml) is a workflow that calls a reusable [Trivy](https://github.com/marketplace/actions/aqua-security-trivy) scan [in this repository](.github/workflows/reusable-trivy-scan-image.yaml).

## This repository is part of my examples on GitHub Actions

- (you are here) [bretfisher/github-actions-templates](https://github.com/BretFisher/github-actions-templates) - Main reusable templates repository
- [bretfisher/super-linter-workflow](https://github.com/BretFisher/super-linter-workflow) - Reusable linter workflow
- [bretfisher/docker-build-workflow](https://github.com/BretFisher/docker-build-workflow)- Reusable docker build workflow
- [bretfisher/docker-ci-automation](https://github.com/BretFisher/docker-ci-automation) - Step by step video and example of a Docker CI workflow
- [My full list of container examples and tools](https://github.com/bretfisher)

## More reading

- [Docker Build/Push Action advanced examples](https://github.com/docker/build-push-action/tree/master/docs/advanced)
- [My full list of container examples and tools](https://github.com/bretfisher)

## 🎉🎉🎉 Join my container DevOps community 🎉🎉🎉

- [My "Vital DevOps" Discord server](https://devops.fan)
- [My weekly YouTube Live show](https://bret.live)
- [My courses and coupons](https://www.bretfisher.com/courses)
