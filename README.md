# terraform-test-workflow

[![ci](https://github.com/atrakic/terraform-test-workflow/actions/workflows/ci.yml/badge.svg)](https://github.com/atrakic/terraform-test-workflow/actions/workflows/ci.yml)

> A reusable Github Actions workflow to test IaC.


# Example usage

```
name: terraform test
on:
  workflow_dispatch: # allow manual trigger
  push:
    branches: [main]
  pull_request:
    branches: [main]
jobs:
  call-tf-reusable-workflow:
    uses: atrakic/terraform-test-workflow/.github/workflows/tf-reusable-workflow.yml@main
    with:
      working_directory: .
```
