# archive-scanner
In the wake of the XZ scandal March 2024; this is an attempt to gain visibility over archives uploaded

## Usage

```yaml
name: Your Job Name

on:
  pull_request:
    types: [opened, synchronize]

permissions:
  issues: write
  pull-requests: write

jobs:
  inspect-archive:
    runs-on: ubuntu-latest
    steps:
      - name: Use My Composite Action
        uses: your-username/your-action-repo@your-branch-name
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

## Required Permissions

To use this action, your workflow must be granted the following permissions:

- `issues: write` - Allows the action to comment on pull requests.
- `pull-requests: write` - Additionally required for managing pull request comments.

You can set these permissions in your workflow file like so:

```yaml
permissions:
  issues: write
  pull-requests: write
```

## Local testing

```
git checkout sample 
act -P ubuntu-latest=catthehacker/ubuntu:act-latest

```
