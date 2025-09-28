# Novem Continuous Integration Workflows

This repository host shared workflows that can be used
for apps build using the Novem workflow.

## Priority Label

For applying priority labels on form issues,
create a `.github/workflows/priorityLabel.yml` file like this:

```yaml
name: Priority Label

permissions:
  issues: write
  
on:
  issues:
    types: [opened, edited]

jobs:
  call-workflow:
    uses: NVMNovem/actions/.github/workflows/priorityLabel.yml@v1
```

## Release

For releasing a new version when the project version changes,
create a `.github/workflows/release.yml` file like this:

```yaml
name: Release

permissions:
  contents: write
  
on:
  push:
    branches:
      - main

jobs:
  call-workflow:
    uses: NVMNovem/actions/.github/workflows/release.yml@v1
    with:
      project_name: YourXcodeProjectName
```

## Update Issue Templates

For updating the issue templates after a new release,
create a `.github/workflows/updateIssueTemplates.yml` file like this:

```yaml
name: Update Issue Templates

permissions:
  contents: write
  
on:
  push:
    branches:
      - main

jobs:
  call-workflow:
    uses: NVMNovem/actions/.github/workflows/updateIssueTemplates.yml@v1
    with:
      templates:
        - Bug
        - Change
```
