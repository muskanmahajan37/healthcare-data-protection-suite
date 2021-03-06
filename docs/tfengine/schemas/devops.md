# Devops Recipe

<!-- These files are auto generated -->

## Properties

### admins_group

Group who will be given org admin access.

Type: string

### billing_account

ID of billing account to attach to this project.

Type: string

### enable_gcs_backend

Whether to enable GCS backend for the devops module.
Defaults to false.

Since the devops module creates the state bucket, it cannot back up
the state to the GCS bucket on the first module. Thus, this field
should be set to false initially.

After the devops module has been applied once and the state bucket
exists, the user should set this to true and regenerate the configs.

To migrate the state from local to GCS, run `terraform init` on the
module.

Type: boolean

### parent_id

ID of parent GCP resource to apply the policy.
Can be one of the organization ID or folder ID according to parent_type.

Type: string

### parent_type

Type of parent GCP resource to apply the policy.
Must be one of 'organization' or 'folder'.

Type: string

### project

Config for the project to host devops resources such as remote state and CICD.

Type: object

### project.apis

List of APIs enabled in the devops project.

NOTE: If a CICD is deployed within this project, then the APIs of
all resources managed by the CICD must be listed here
(even if the resources themselves are in different projects).

### project.owners

List of members to transfer ownership of the project to.
NOTE: By default the creating user will be the owner of the project.
Thus, there should be a group in this list and you must be part of that group,
so a group owns the project going forward.

Type: array(string)

### project.project_id

ID of project.

Type: string

### state_bucket

Name of Terraform remote state bucket.

Type: string

### storage_location

Location of state bucket.

Type: string
