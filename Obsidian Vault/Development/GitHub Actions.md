
> [!NOTE]
> Workflows are place in the repository at `.github/workflows/`
> 
> Custom actions can be placed in:
> - Specific repository that contains only actions at root
> - Current repository at: `.github/actions/<custom-name>/action.yml`

```yml
# Name of workflow
name: Workflow functionalities
# When the workflow is triggered
# workflow_dispatch - manual triggered
# Doc: https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows
on: workflow_dispatch

# Run each job in parallel by default
jobs:

# Basic functionality

  # Job name
  first-job:
    # Environment for the job to run
    # https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners/about-github-hosted-runners
    runs-on: ubuntu-latest
    # Like tasks in Ansible; simple commands
    steps:
      # Name of the step
      - name: Print greeting
        # An action (like module)
        # Run: shell command
        run: echo "Hello World!"

# Using implemented action + Artifacts

  # Runs in parallel with 'first-job'
  second-job:
    runs-on: ubuntu-latest
    steps:
      - name: Download code
        # Runs an action defined on a github repository / local
        uses: actions/checkout@v4
	  - name: Upload artifacts
        uses: actions/upload-artifact@v4
        # 'Arguments' for the action
        with:
          # Name of artifact
          name: my-code
          # Files to be added to artifact.
          # Here will add the entire project
          path: .

# Controlling workflow + Using Artifacts

  # Waits for 'second-job' to finish succesfully
  third-job:
    needs: second-job
    runs-on: ubuntu-latest
    steps:
     - name: Get build artifacts
        uses: actions/download-artifact@v4
        with:
          # Same name as upload artifacts
          name: my-code
      - name: Install NodeJS
        uses: actions/setup-node@v4
        # 'Arguments' for the action
        with:
          node-version: 18
```

