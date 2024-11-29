[![Release Status](https://github.com/mundoalem/action-prepare/actions/workflows/pipeline.yml/badge.svg)](https://github.com/mundoalem/action-prepare/actions/workflows/pipeline.yml)

# Prepare

Prepare is a GitHub action used to setup the dependencies needed by specific project types and their pipeline jobs. The
currently supported project types and jobs are:


| Project Type | Jobs               | OS    |
| ------------ | ------------------ | ----- |
| container    | cd, ci, lint, scan | linux |
| nix          | ci                 | linux |

# Inputs

| Input             | Description                          | Required | Default |
| ----------------- | ------------------------------------ | -------- | ------- |
| job               | Job we are preparing for             | Yes      |         |
| type              | Project type we are preparing for    | Yes      |         |
| version_alejandra | Version of alejandra to be installed | No       | 3.1.0   |
| version_checkov   | Version of checkov to be installed   | No       | 3.2.322 |
| version_hadolint  | Version of hadolint to be installed  | No       | 2.12.0  |
| version_task      | Version of task to be installed      | No       | 3.40.0  |

# Outputs

None.

# Example Usage

Setting up the `cd` job of a `container` project type:

```yaml
- name: Prepare
  uses: mundoalem/action-prepare@v1
  with:
    type: container
    job: cd
```

Setting up the `lint` job of a `container` project type with a specific version of `hadolint`:

```yaml
- name: Prepare
  uses: mundoalem/action-prepare@v1
  with:
    type: container
    job: lint
    version_hadolint: 2.10.0
```

# License

[GNU General Public License Version 3](https://github.com/mundoalem/action-prepare/blob/main/LICENSE)
