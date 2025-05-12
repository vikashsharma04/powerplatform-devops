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
