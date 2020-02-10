# terraform-aws-polkadot-network

## Features

This module sets up VPCs, DNS zones, and security groups for running validator nodes on polkadot.

## Terraform versions

For Terraform v0.12.0+

## Usage

```
module "this" {
    source = "github.com/insight-infrastructure/terraform-aws-polkadot-network"
}
```

## Examples

- [simple](https://github.com/insight-infrastructure/terraform-aws-polkadot-network/tree/master/examples/simple)

## Known issues
No issue is creating limit on this module.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| azs | List of availability zones | `list(string)` | <pre>[<br>  "us-east-1a",<br>  "us-east-1b",<br>  "us-east-1c"<br>]</pre> | no |
| bastion\_enabled | Boolean to enable a bastion host.  All ssh traffic restricted to bastion | `bool` | `false` | no |
| bastion\_sg\_name | Name for the bastion security group | `string` | `"bastion-sg"` | no |
| consul\_enabled | Boolean to allow consul traffic | `bool` | `false` | no |
| consul\_sg\_name | Name for the consult security group | `string` | `"consul-sg"` | no |
| corporate\_ip | The corporate IP you want to restrict ssh traffic to | `string` | `""` | no |
| create\_internal\_domain | Boolean to create an internal split horizon DNS | `bool` | `false` | no |
| create\_public\_regional\_subdomain | Boolean to create regional subdomain - ie us-east-1.example.com | `bool` | `false` | no |
| environment | The environment | `string` | `""` | no |
| hids\_enabled | Boolean to enable intrusion detection systems traffic | `bool` | `false` | no |
| hids\_sg\_name | Name for the HIDS security group | `string` | `"hids-sg"` | no |
| internal\_tld | The top level domain for the internal DNS | `string` | `"internal"` | no |
| logging\_enabled | Boolean to allow logging related traffic | `bool` | `false` | no |
| logging\_sg\_name | Name for the logging security group | `string` | `"bastion-sg"` | no |
| monitoring\_enabled | Boolean to for prometheus related traffic | `bool` | `false` | no |
| monitoring\_sg\_name | Name for the monitoring security group | `string` | `"monitoring-sg"` | no |
| namespace | The namespace to deploy into | `string` | `""` | no |
| network\_name | The network name, ie kusama / mainnet | `string` | `""` | no |
| owner | n/a | `string` | `""` | no |
| public\_node\_sg\_name | Name for the public node security group | `string` | `"public-sg"` | no |
| root\_domain\_name | The public domain | `string` | `""` | no |
| stage | The stage of the deployment | `string` | `""` | no |
| vault\_enabled | Boolean to allow vault related traffic | `bool` | `false` | no |
| vault\_sg\_name | Name for the vault security group | `string` | `"bastion-sg"` | no |
| vpc\_name | The name of the VPC | `string` | `""` | no |
| zone\_id | The zone ID to configure as the root zoon - ie subdomain.example.com's zone ID | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| vpc\_id | n/a |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Authors

Module managed by [{{ cookiecutter.owner }}](github.com/{{ cookiecutter.owner }})

## Credits

- [Anton Babenko](https://github.com/antonbabenko)

## License

Apache 2 Licensed. See LICENSE for full details.