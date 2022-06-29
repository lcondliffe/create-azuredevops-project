# Ansible Playbook - Create Azure DevOps Project

Playbook to automate the creation of an Azure DevOps project to ensure that RBAC assignments are applied correctly for all newly created projects.

## Pre-Requisites

- You need a personal access token with full access to the target project to use with the Azure DevOps API. This must be passed to the playbook as variable *azure_devops_api_token*

## Usage

- Set variables *azure_devops_organisation*, *azure_devops_project_name*, *azure_devops_project_description* with the details for the new project. Include any additional ROLE groups to *azure_devops_groups* that need to be project adminstrators.

`ansible-playbook main.yml --extra-vars=@vars.yml`
