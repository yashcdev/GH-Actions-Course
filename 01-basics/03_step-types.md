# Step Types

Steps can be:

- inline / local ("run")
- actions ("uses")

# Uses

- The uses keyword tells GitHub Actions to run an existing action instead of writing the commands yourself.
- Think of an action as a reusable piece of code that someone has already built.

Note:
We can also specify a version tag or commit hash for the action

# With

- The with keyword lets you pass input values to the action.
- For understanding, consider action to be a function that does some operation, and with is the parameter given to that function while calling it
