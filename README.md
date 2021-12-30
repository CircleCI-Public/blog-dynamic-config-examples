# Blog Dynamic Config Examples using Setup Workflows

This repo maintains the examples from the [Dynamic Config blog post][1] which will be published soon.

## Perquisites

This code example leverages Orbs and other tools which require you to have accounts and api tokens for those tools. You need to have accounts in the following services to use this example:

- Create a [DigitalOcean Account][11]
  - Generate a [DigitalOcean API Token][13]
  - **Optional:** Install the [DigitalOcean doctl command line tool][14] locally
- Install [Terraform CLI][4] locally
  - Create a [Terraform Cloud Account][5]
  - Create a new [Terraform Cloud organization][6]
  - Create 2 new [Terraform Cloud workspaces][7] named `iac_do` and `deploy-iac-do` and choose the `"No VCS connection"` option
  - Enable [local execution mode][9] in both newly created workspaces
  - Create a new [Terraform API token][8]
- [Snyk account API Token][16]
- [Docker Hub account and create an API token][17]
- Sign-up for a [CircleCI][10] account

## Create pipeline project environment variables

[Create these environment variables][18] your your pipeline project with the appropriate values you captured in the Prerequisites section and **do NOT** prefix them with a `$` character:

```
DIGITAL_OCEAN_TOKEN
DOCKER_LOGIN
DOCKER_PASSWORD
SNYK_TOKEN
TERRAFORM_TOKEN
```

## Project structure

- `.circleci/` directory holds the config.yml file which implements Setup Workflows
- `terraform/` directory hold the Terraform code
- `scripts/` directory holds the scripts that generate config.yml files

[1]: https://circleci.com/blog/building-cicd-pipelines-using-dynamic-config/
[2]: https://circleci.com/blog/our-cloud-platform-your-compute-introducing-the-circleci-runner/
[3]: https://github.com/CircleCI-Public/blog-runner
[4]: https://www.terraform.io/docs/cli-index.html
[5]: https://app.terraform.io/signup/account
[6]: https://learn.hashicorp.com/terraform/cloud-getting-started/signup#create-your-organization
[7]: https://learn.hashicorp.com/terraform/cloud-getting-started/create-workspace
[8]: https://learn.hashicorp.com/terraform/tfc/tfc_migration#authenticate-with-terraform-cloud
[9]: https://www.terraform.io/docs/cloud/workspaces/settings.html#execution-mode
[10]: https://circleci.com/signup/
[11]: https://try.digitalocean.com/freetrialoffer/
[12]: https://www.digitalocean.com/docs/droplets/how-to/add-ssh-keys/to-account/
[13]: https://www.digitalocean.com/docs/apis-clis/api/create-personal-access-token/
[14]: https://www.digitalocean.com/docs/apis-clis/doctl/how-to/install/
[15]: https://snyk.io/docs/getting-started/
[16]: https://snyk.io/blog/service-accounts/
[17]: https://docs.docker.com/docker-hub/access-tokens/
[18]: https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project
