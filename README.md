# terraform-equinix-template

<!-- TEMPLATE: Review all "TEMPLATE" comments and remove them when applied. -->
<!-- TEMPLATE: replace "template" with the name of your project. The prefix "terraform-equinix-" informs the Terraform registry that this project is a Terraform module associated with the Equinix provider, preserve this prefix. -->
[![Experimental](https://img.shields.io/badge/Stability-Experimental-red.svg)](https://github.com/equinix-labs/standards#about-uniform-standards)
[![run-pre-commit-hooks](https://github.com/equinix-labs/terraform-equinix-template/actions/workflows/pre-commit.yaml/badge.svg)](https://github.com/equinix-labs/terraform-equinix-template/actions/workflows/pre-commit.yaml)
[![generate-terraform-docs](https://github.com/equinix-labs/terraform-equinix-template/actions/workflows/documentation.yaml/badge.svg)](https://github.com/equinix-labs/terraform-equinix-template/actions/workflows/documentation.yaml)

`terraform-equinix-template` is a minimal Terraform module that utilizes [Terraform providers for Equinix](https://registry.terraform.io/namespaces/equinix) to provision digital infrastructure and demonstrate higher level integrations.

<!-- TEMPLATE: Insert an image here of the infrastructure diagram. You can generate a starting image using instructions found at https://www.terraform.io/docs/cli/commands/graph.html#generating-images -->

## Usage

This project is experimental and supported by the user community. Equinix does not provide support for this project.

Install Terraform using the [tfenv](https://github.com/tfutils/tfenv) utility.

This project may be forked, cloned, or downloaded and modified as needed as the base in your integrations and deployments.

This project may also be used as a [Terraform module](https://learn.hashicorp.com/collections/terraform/modules).

To use this module in a new project, create a file such as:

```hcl
# main.tf
terraform {
  required_providers {
    equinix = {
      source = "equinix/equinix"
    }
}

module "example" {
  source = "github.com/equinix-labs/template"
  # TEMPLATE: replace "template" with the name of the repo after the terraform-equinix- prefix.

  # Published modules can be sourced as:
  # source = "equinix-labs/template/equinix"
  # See https://www.terraform.io/docs/registry/modules/publish.html for details.

  # version = "0.1.0"

  # TEMPLATE: insert required variables here
}
```

Install [pre-commit](https://pre-commit.com/#install) with its prerequesites: [python](https://docs.python.org/3/using/index.html) and [pip](https://pip.pypa.io/en/stable/installation/).

Configure pre-commit: `pre-commit install`.

Install required packages: [tflint](https://github.com/terraform-linters/tflint), [tfsec](https://aquasecurity.github.io/tfsec/v1.0.11/getting-started/installation/), [shfmt](https://github.com/mvdan/sh), [shellcheck](https://github.com/koalaman/shellcheck), and [markdownlint](https://github.com/markdownlint/markdownlint).

Run `terraform init -upgrade` and `terraform apply`.

## Module Documentation

The main README.md, the modules README.md and the examples README.md are populated by [terraform-docs worflow job](.github/workflows/documentation.yaml). The following sections are appended between the terraform-docs delimeters: Requiremenents, Providers, Modules, Resources, Inputs, and Outputs.

## Module Release and Changelog Generation

The module git release and [changelog](CHANGELOG.md) are generated by the [release workflow job](.github/workflows/release.yaml). The release worflow follows the [conventional commits convention](https://www.conventionalcommits.org/). To submit a commit, please follow the [commit message format guidelines](https://www.conventionalcommits.org/en/v1.0.0/#specification). This job is set to run manually by default.

## Github PR Title

The title of the PR must conform with the [commit message format guidelines](https://www.conventionalcommits.org/en/v1.0.0/#specification). PR title must start with an upper case character. The following keywords may be used in the title of the PR:

- fix: must be used when commits represent a bug fix
- feat: must be used when commits represent a new feature
- docs: represents documentation only changes
- ci: represents hanges to CI configuration files and scripts
- chore: represents a mainteance chore
- [WIP]: represents a work-in-progress PR

Please see [conventional commit message examples](https://www.conventionalcommits.org/en/v1.0.0/#examples).

## Examples

To view examples for how you can leverage this module, please see the [examples](examples/) directory.

<!-- TEMPLATE: The following block has been generated by terraform-docs util: https://github.com/terraform-docs/terraform-docs -->
<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.3 |
| <a name="requirement_equinix"></a> [equinix](#requirement\_equinix) | >= 1.10.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_equinix"></a> [equinix](#provider\_equinix) | >= 1.10.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_inline_module"></a> [inline\_module](#module\_inline\_module) | ./modules/inline-module | n/a |

## Resources

| Name | Type |
|------|------|
| [equinix_metal_device.example_device](https://registry.terraform.io/providers/equinix/equinix/latest/docs/resources/metal_device) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_metal_auth_token"></a> [metal\_auth\_token](#input\_metal\_auth\_token) | The example auth token value defines what will be included in the example resource in main.tf. This example is descriptive. | `string` | n/a | yes |
| <a name="input_metal_project_id"></a> [metal\_project\_id](#input\_metal\_project\_id) | The example project id value defines what will be included in the example resource in main.tf. This example is descriptive. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_device_hostname"></a> [device\_hostname](#output\_device\_hostname) | The example output. In practice, output value reference implicit resource attributes declared in main.tf |
| <a name="output_gateway_id"></a> [gateway\_id](#output\_gateway\_id) | The example output. In practice, output value reference implicit resource attributes declared in main.tf |
<!-- END_TF_DOCS -->
## Contributing

If you would like to contribute to this module, see [CONTRIBUTING](CONTRIBUTING.md) page.

## License

Apache License, Version 2.0. See [LICENSE](LICENSE).
<!-- TEMPLATE: Expand this section with any additional information or requirements. -->
