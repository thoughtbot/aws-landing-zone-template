# Landing Zone Template

Template repository for AWS organizations following thoughtbot's best practices.
Applying this template to your new AWS Control Tower organization will:

- Configure standard AWS accounts for running Flightdeck and associated services
- Deploy [customizations for AWS Control Tower]
- Configure a Hub and spoke setup for Terraform CI/CD

## Getting Started

Before using this repository, you must already have an AWS organization with
managed by [AWS Control Tower].

1. Create a new repository for this template.
2. Run the included `bin/deploy` script to set up your organization.
3. `bin/deploy` will render the accounts and manifest templates, interpolate
the necessary strings into place, and convert both templates into yaml files. You
will have the option to edit each file before deploying to AWS.

## Accounts

See [accounts] for information about accounts provisioned by this template.


## Troubleshooting

Review the AWS documentation on [common errors] and possible solutions


[AWS Control Tower]: https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html
[customizations for AWS Control Tower]: https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/
[common errors]: https://docs.aws.amazon.com/controltower/latest/userguide/troubleshooting.html
[accounts]: accounts.md
