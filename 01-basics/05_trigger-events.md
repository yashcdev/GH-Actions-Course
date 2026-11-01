# Trigger Events

The GitHub workflow can be started / triggered using any event.

- Trigger manually
- Push to branch
- Create / update a Pull request (PR)
- Cron Schedule, etc.

## 1\. Push

- Workflow is triggered when commits are pushed to a branch.
- You can configure which branches, tags and file changes should trigger the workflow.\
  a. When you push to a branch / branches\
  b. When specific git tags are pushed\
  c. When files change

yml

```yml
on:
  push:
    branches:
      - "example-branch/*"
    paths-ignore:
      - "docs/**"
```

**Note:** You can add a list of branches and paths (files) to ignore / include for running the workflow.

## `*` vs `**`

### Example: Directory Structure

text

```
03-core-features/
└── filters/
    ├── trim.md
    ├── config.md
    ├── advanced/
    │   ├── normalize.md
    │   └── validate.md
    └── advanced/
        └── rules/
            └── custom.md
```

### `*`

yml

```
paths:
  - "03-core-features/filters/*.md"
```

Will consider:

- `filters/trim.md` ✅
- `filters/config.md` ✅
- `filters/advanced/normalize.md` ❌
- `filters/advanced/rules/custom.md` ❌

### `**`

yml

```
paths:
  - "03-core-features/filters/**/*.md"
```

Will consider:

- `filters/trim.md` ✅
- `filters/config.md` ✅
- `filters/advanced/normalize.md` ✅
- `filters/advanced/validate.md` ✅
- `filters/advanced/rules/custom.md` ✅

## 2\. Pull request

- You can configure for which pull requests you want to run the workflow.\
  a. When a PR is opened, closed, etc.\
  b. When a PR targets a specific branch for merge\
  c. When a PR includes changes to specific files

**Note:** You can add a list of branches and paths (files) to ignore / include for running the workflow.

yml

```
pull_request:
  types:
    - opened
    - synchronize
    - reopened
  paths:
    - "03-core-features/filters/*.md"
    - ":03-core-features/filters/*.txt"
```

## 3. Cron

It is a time based job-scheduler that can automatically execute a task at a specific time / recurring intervals

```
* * * * *
| | | | |
| | | | └── Day of week
| | | └──── Month
| | └────── Day of month
| └──────── Hour
└────────── Minute
```

Cron expression

Execution time

0 0 \* \* \*

Every day at 12:00 AM

0 9 \* \* \*

Every day at 9:00 AM

0 _/2 _ \* \*

Every 2 hours

0 0 \* \* 1

Every Monday at midnight

0 0 1 \* \*

First day of every month

_/5 _ \* \* \*

Every 5 minutes

```

```

# Default Environment variables

The default environment variables that GitHub sets are available to every step in a workflow.
These are used to use a value into a shell command

Some examples are:
$GITHUB_EVENT_NAME
$GITHUB_EVENT_PATH

# GitHub Glob Patterns

- Glob patterns are used to match multiple file or directory paths without having to specify every file individually.
- In GitHub Actions, they are particularly useful for controlling when a workflow should run based on which files have changed.

1. Match multiple file extensions

```yml
paths:
  - "03-core-features/filters/**/*.{md,txt,yml}"
```

2. Match files starting with a particular name

```yml
paths:
  - "03-core-features/filters/test\*.md"
```
