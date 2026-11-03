# Environment Variables

- Variables within the execution environment
- They can be scoped with -> workflow, job, step

## Note:

- Variables defined at the workflow level are available everywhere.
- Variables defined on a job only exist inside that job.
- Step-level variables override job and workflow values but vanish once the step completes.
- Use ${{ env.VAR_NAME }} when you need to reference a variable from YAML configuration (for example inside an if: condition).
