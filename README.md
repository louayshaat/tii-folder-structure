# TII Folder structure using Terraform

## Recommendation for setting up the terrafoirm project in GCP
Please follow this [recommendations](https://cloud.google.com/docs/terraform/best-practices/general-style-structure) from google in setting up the structure

## terraform-google-folders
This module helps create several folders under the same parent, enforcing consistent permissions, and with a common naming convention.
The resources/services/activations/deletions that this module will create/trigger are:

- Create folders with the provided names
- Assign the defined permissions to the provided list of users or groups.

