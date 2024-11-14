# Reusable Workflows

The main goal of the Workflow Manager is to provide a centralized solution for managing GitHub Actions workflows for multiple backend and frontend repositories in our microservices architecture. 
Instead of updating workflows in each individual repository by cloning and open PR from local env, make the changes in this repository and all repositories will be updated.

## Key Features

- **Centralized management** of workflows.
- **Automatic propagation** of workflow updates across all connected repositories.
- Simplifies the process of updating workflow configurations (e.g., secrets, input variables).
- Reduces the need for manual changes in multiple repositories, improving consistency.

## How It Works

Whenever changes are made to workflows in the **reusable** folder, an automated pipeline is triggered to push these changes to all repositories and open a pull request.

### Workflow Update Process

1. **Update or Change the Workflow**  
   Make the necessary changes to the reusable workflow(s) in this repository (e.g., update input variables, secrets, etc.).

2. **Create a Pull Request**  
   Once the changes are made, create a Pull Request (PR) for the update.

3. **Merge the PR**  
   After the PR is reviewed and approved, merge it into the `main` branch.

4. **Automatic Workflow Update**  
   Upon merging, an automated update process is triggered, this process pushes the workflow changes to **all repositories** by creating a branch with the same id from your merged PR.

5. **Check PRs and Ask for Reviews**  
   Then will create a Pull Requests in each repositories with the updated workflows and the title from the current merged PR. The merge into the respective repositories will be made manually.

## Benefits

- **Consistency**: Ensures all repositories use the latest version of workflows.
- **Efficiency**: Reduces the effort required to maintain and update workflows across multiple repositories.
- **Automation**: Streamlines the process of propagating changes, minimizing manual work.
