# Landing Zone

Before using this repository, you must already have an AWS organization with
managed by [AWS Control Tower].

This repository contains configuration for your AWS landing zone. The changes
are applied using [customizations for AWS Control Tower]. You can use the
included `bin/deploy` script to bootstrap your organization and deploy
customizations.

## Editing

### Accounts

Accounts are provisioned using the AWS Control Tower account factory. To add a
new account to the landing zone, add a new entry in `accounts.yaml`.

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

[AWS Control Tower]: https://albaik.awsapps.com/start/#/
[customizations for AWS Control Tower]: https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/
