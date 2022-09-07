## Impossible Research Common Workflows

### lint

Runs `pre-commit` checks

```yaml
---
name: 👷 Continuous Integration

on:  # yamllint disable-line rule:truthy
  pull_request:
    branches: ["master"]

jobs:
  lint:
    uses: impossible-research/common-workflows/.github/workflows/lint.yaml@master
```


### plan

Runs `terraform plan`

```yaml
---
name: 👷 Continuous Integration

on:  # yamllint disable-line rule:truthy
  pull_request:
    branches: ["master"]

jobs:
  plan:
    uses: impossible-research/common-workflows/.github/workflows/plan.yaml@master
    with:
      tf_path: infra
    secrets:
      TF_API_TOKEN: ${{ secrets.TF_API_TOKEN }}
```
