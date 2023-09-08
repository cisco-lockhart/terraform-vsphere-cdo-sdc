# Example usage of terraform-vsphere-cdo-sdc

To use this example, you will need a CDO tenant and API token in addition to the requirements specified in the README at the root of this repository, as we will be using the Terraform CDO provider.

## Pre-requisites

- Log in to your CDO account in the [US](https://www.defenseorchestrator.com), the [EU](https://www.defenseorchestrator.eu), or the [Asia-Pacific and Japan region](https://apj.cdo.cisco.com).
- Create an [API-only user](https://docs.defenseorchestrator.com/c-delete-a-user-record-for-a-user-role.html#!t-create-api-only-users.html).
- Set the values for `cdo_base_url`, `cdo_api_token`, and `cdo_tenant_name`, either using environment variables with the `TF_VAR_` prefix or by specifying a default.
- Set the values for all of the vSphere-specific resources, either using environment variables with the `TF_VAR_` prefix or by specifying a default.

Note: you can update the environment variables in `terraform_env_vars.sh.sample` and source that into your shell if you like.

## Run Terraform

- Initialise the modules by running
```
terraform init
```
- Create and review a plan
```
terraform plan -out plan.out
```
- Apply the saved plan
```
terraform apply plan.out
```