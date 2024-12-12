# TII Folder structure using Terraform

## Recommendation for setting up the terrafoirm project in GCP
Please follow this [recommendations](https://cloud.google.com/docs/terraform/best-practices/general-style-structure) from google in setting up the structure

## terraform-google-folders
This module helps create several folders under the same parent, enforcing consistent permissions, and with a common naming convention.
The resources/services/activations/deletions that this module will create/trigger are:

- Create folders with the provided names
- Assign the defined permissions to the provided list of users or groups.

### Usage
Basic usage of this module is as follows:

```
module "folders" {
  source  = "terraform-google-modules/folders/google"
  version = "~> 5.0"

  parent  = "folders/65552901371"

  names = [
    "dev",
    "staging",
    "production",
  ]

  set_roles = true

  per_folder_admins = {
    dev = {
      members = [
        "group:gcp-developers@domain.com"
      ],
    },
    staging = {
      members = [
        "group:gcp-qa@domain.com"
      ],
    }
    production = {
      members = [
        "group:gcp-ops@domain.com"
      ],
    }
  }

  all_folder_admins = [
    "group:gcp-security@domain.com",
  ]
}

```
## Examples
This folder [Folder Structure examples](/examples/) has a few examples that you can use to get started
