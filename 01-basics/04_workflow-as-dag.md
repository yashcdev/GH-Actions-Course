# Workflows with DAG

- The jobs can run one after the other or in a specific order (like nodes)
- Just like a DAG (Directed Acyclic Graph)
- This means that the flow cannot be circular (no loop)
- This helps us to take outputs from one job and pass them to another as well

Note:
The needs object specifies the structure
