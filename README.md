Power Platform DevOps
Description: Power Platform DevOps for exporting unmanaged solutions.

Repository Details
Repository Name: powerplatform-devops
Owner: vikashsharma04
Repository ID: 982225505
Purpose
This repository is designed to enable DevOps for Power Platform by automating the process of exporting unmanaged solutions. It includes workflows for exporting solutions from a development environment, unpacking them, preparing them, and committing the changes to a Git branch.

Key Features
Export Unmanaged Solutions: Automates the export process from Power Platform environments.
Workflow Automation: Includes GitHub Actions workflows to handle solution export, unpacking, and version control.
Git Integration: Automatically commits and pushes exported solutions to the repository.
GitHub Actions Workflow
The repository includes a workflow named export-and-commit-solution, which performs the following tasks:

Verifies the connection to the Power Platform environment.
Exports the specified solution as an unmanaged ZIP file.
Unpacks the solution into a folder structure suitable for source control.
Commits and pushes the changes to the main branch.
Workflow File
The workflow file is located at .github/workflows/export-and-commit-solution.yml. You can view it here.

Workflow Inputs
Solution Name: The name of the solution to be exported (default: ADCBMasterConfigurations).
Environment Variables
The workflow uses the following environment variables for authentication and configuration:

ENVIRONMENT_URL: URL of the Power Platform environment.
CLIENT_ID: Application (client) ID for authentication.
TENANT_ID: Tenant ID for authentication.
Secrets
The workflow requires the following GitHub secrets:

PowerPlatformSPN: The client secret for authentication.
GITHUB_TOKEN: Token for pushing changes to the repository.
Known Issue and Solution
Issue:
The workflow may fail due to a timeout while downloading the microsoft/powerplatform-actions action.

Solution:
Update the workflow to use the latest stable version of the action (@v0) instead of a specific commit SHA.
Ensure network stability and retry if the issue persists.

### Git Commands with Examples

Below are the Git commands commonly used in this repository along with examples:

#### 1. Clone the Repository
To clone the repository to your local machine:
```bash
git clone https://github.com/vikashsharma04/powerplatform-devops.git
```

#### 2. Check Repository Status
To check the current status of your repository:
```bash
git status
```

#### 3. Add Changes to Staging
To stage changes for commit:
```bash
git add .
```

#### 4. Commit Changes
To commit staged changes with a message:
```bash
git commit -m "Your commit message here"
```

#### 5. Push Changes to Remote
To push committed changes to the remote repository:
```bash
git push origin main
```

#### 6. Pull Latest Changes
To pull the latest changes from the remote repository:
```bash
git pull origin main
```

#### 7. Create a New Branch
To create and switch to a new branch:
```bash
git checkout -b new-branch-name
```

#### 8. Switch to an Existing Branch
To switch to an existing branch:
```bash
git checkout branch-name
```

#### 9. Merge a Branch
To merge a branch into the current branch:
```bash
git merge branch-name
```

#### 10. View Commit History
To view the commit history:
```bash
git log
```

#### 11. Discard Changes
To discard unstaged changes in a file:
```bash
git checkout -- file-name
```

#### 12. Delete a Branch
To delete a branch locally:
```bash
git branch -d branch-name
```
To delete a branch remotely:
```bash
git push origin --delete branch-name
```

#### 13. Resolve Merge Conflicts
To resolve merge conflicts, edit the conflicting files, stage the changes, and commit:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

#### 14. Revert a Commit
To revert a specific commit:
```bash
git revert commit-hash
```

#### 15. Reset to a Previous Commit
To reset the repository to a previous commit:
```bash
git reset --hard commit-hash
```

These commands will help you manage the repository effectively while working with the Power Platform DevOps workflows.
