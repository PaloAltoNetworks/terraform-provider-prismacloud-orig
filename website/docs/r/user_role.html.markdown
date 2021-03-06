---
layout: "prismacloud"
page_title: "Prisma Cloud: prismacloud_user_role"
description: |-
  Manage an user role.
---

# prismacloud_user_role

Manage an user role.

## Example Usage

```hcl
resource "prismacloud_user_role" "example" {
    name = "my user role"
    description = "Made by Terraform"
    role_type = "Account Group Admin"
}
```

## Argument Reference

* `name` - (Required) Name of the role.
* `description` - (Optional) Description.
* `role_type` - (Required) User role type.  Valid valies are `System Admin`, `Account Group Admin`, `Account Group Read Only`, `Cloud Provisioning Admin`, or `Account and Cloud Provisioning Admin`.
* `account_group_ids` - (Optional) List of accessible account group IDs.
* `associated_users` - (Optional) List of associated application users which cannot exist in the system without the user role.
* `restrict_dismissal_access` - (Optional, bool) Restrict dismissal access.

## Attribute Reference

* `role_id` - Role UUID.
* `last_modified_by` - Last modified by
* `last_modified_ts` - (int) Last modified timestamp.
* `account_groups` - List of account groups, as defined [below](#account-groups).

### Account Groups

Each account group has the following attributes.

* `group_id` - The group ID.
* `name` - Group name.

## Import

Resources can be imported using the role ID:

```
$ terraform import prismacloud_user_role.example 11111-22-33
```
