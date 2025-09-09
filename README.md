# terraform-test-workflow

[![ci](https://github.com/atrakic/terraform-test-workflow/actions/workflows/ci.yml/badge.svg)](https://github.com/atrakic/terraform-test-workflow/actions/workflows/ci.yml)

> A reusable Github Actions workflow to test IaC.


# Example usage

```
name: terraform test
on:
  workflow_dispatch: # allows manual trigger
  push:
  pull_request:
    branches: [main]

jobs:
  terraform-test-workflow:
    uses: atrakic/terraform-test-workflow/.github/workflows/tf-reusable-workflow.yml@main
    with:
      working_directory: ./tf
      runs_on: ubuntu-latest
      environment: dev
      terraform_version: "~>1.0"
      terraform_fmt_enabled: true
      terraform_fmt_check: false
      terraform_test_enabled: true
      terraform_test_args: null   ##  eg. "-var 'foo=bar' -filter=tests/mock_plan.tftest.hcl"
```
