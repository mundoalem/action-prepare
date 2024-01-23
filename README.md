[![Release Status](https://github.com/sbpdvb/dtaplatform-action-prepare/actions/workflows/pipeline.yml/badge.svg)](https://github.com/sbpdvb/dataplatform-action-prepare/actions/workflows/pipeline.yml)

# Prepare

Prepare is a GitHub action used to setup the dependencies needed by specific project types and their pipeline jobs. The
currently supported project types and jobs are:

| Project Type | Jobs               | OS    |
| ------------ | ------------------ | ----- |
| container    | cd, ci, lint, scan | linux |

# Inputs

| Input            | Description                         | Required | Default |
| ---------------- | ----------------------------------- | -------- | ------- |
| job              | Job we are preparing for            | Yes      |         |
| type             | Project type we are preparing for   | Yes      |         |
| version_checkov  | Version of checkov to be installed  | No       | 3.1.69  |
| version_hadolint | Version of hadolint to be installed | No       | 2.12.0  |

# Outputs

None.

# Example Usage

Setting up the `cd` job of a `container` project type:

```yaml
- name: Prepare
  uses: sbpdvb/action-prepare@v1
  with:
    type: container
    job: cd
```

Setting up the `lint` job of a `container` project type with a specific version of `hadolint`:

```yaml
- name: Prepare
  uses: sbpdvb/action-prepare@v1
  with:
    type: container
    job: lint
    version_hadolint: 2.10.0
```