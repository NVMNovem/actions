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
