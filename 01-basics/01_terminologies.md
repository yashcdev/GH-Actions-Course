# Concepts and Terminology

1. GitHub Events

- Any event by which we trigger the workflow or the pipeline
- It uses github apis, eg; on push, etc.

2. Workflow

- Pipeline terminology for GitHub Actions
- So the file we write represents a workflow

3. Job

- The workflow can contain multiple jobs
- Job is a set of steps that will be executing on a remote machine
- the environment / machine is different

4. Steps

- Steps are instructions in the Job that will execute
- the environment / machine is the same

5. Runner

- The actual server environment that will execute the Jobs

# Hierarchy

```
Workflow
    Job
        Step
```
