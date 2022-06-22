# Ansible Playbook - Create Azure DevOps Project

Playbook to automate the creation of an Azure DevOps project to ensure that RBAC assignments are applied correctly for all newly created projects.

## Pre-Requisites

- You need a personal access token with full access to the target project to use with the Azure DevOps API. This must be passed to the playbook as variable *azure_devops_api_token*

- If using this playbook to create the default_vars variable group:
    - You need to have Azure CLI installed and logged in using *az login*
    - You need to have the Azure DevOps Azure CLI extension installed:

        `az extension add --name azure-devops`



## Usage

- Set variables *azure_devops_organisation*, *azure_devops_project_name*, *azure_devops_project_description* with the details for the new project. Include any additional ROLE groups to *azure_devops_groups* that need to be project adminstrators.

`ansible-playbook main.yml --extra-vars=@vars.yml`

## default_vars variable group

Optionally, you can include the default_vars variable group if the Azure DevOps project will need some pre-defined variables in the library for pipelines.

Populate the *vargroup_default_vars* variable in vars.yml with values created during vault AppRole configuration to automatically create the variable group with the Azure DevOps project.