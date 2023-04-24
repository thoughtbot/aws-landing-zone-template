# Landing Zone

This repository contains configuration as code for the AWS organization
managed by [AWS Control Tower]. The changes are applied using [customizations
for AWS Control Tower]. You can use the included `bin/deploy` script to
bootstrap your organization and deploy customizations.

You must have administrator access to the Management account to run scripts in
this repository.

## Editing

### Accounts

Accounts are provisioned using the AWS Control Tower account factory. To add a
new account to the landing zone, add a new entry in `accounts.yaml`.

See [accounts] for information about accounts provisioned by this template.

### Permissions

Permissions are defined as [IAM permission sets] and defined in
`permissions/manifest.yaml`.

### Service Control Policies

Service control policies are specified as JSON and provisioned using the
Customizations for Control Tower pipeline. To add a new service control policy,
add a template in `policies` and modify `manifest.yaml` to reference the new
policies.

### Baseline

Account baselines are specified as CloudFormation templates and provisioned
using the Customizations for Control Tower pipeline. To add resources to the
account baseline, add a template in `templates` and modify `manifest.yaml` to
reference the new template.

## Deploying

Run `bin/deploy` to setup and deploy all resources. The first time you deploy,
the script will prompt for details about your AWS SSO organization and Git
repository, deploy Customizations for Control Tower, save a configuration for
your landing zone to avoid prompting in the future. You can commit this file to
Git.

[AWS Control Tower]: https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html
[customizations for AWS Control Tower]: https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/
[IAM permission sets]: https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsetsconcept.html
[accounts]: ./accounts.md
