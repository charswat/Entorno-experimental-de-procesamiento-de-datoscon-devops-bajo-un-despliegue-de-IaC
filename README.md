# Experimental environment of distributed data processing integrating devops, under a deployment of infrastructure as code in the cloud.
Implementation of an architecture for a distributed data processing cluster, integrating Devops into a software delivery cycle; through an automated deployment of code-like infrastructure in the cloud.
## Archtecture
![Diagrama sin título-Page-4 drawio (1)](https://user-images.githubusercontent.com/72947118/230431114-216ab148-dccf-45c5-b8c5-54f02cd2ba2e.png)

## Student interaction with architecture

![arquitectura big data-Page-4 drawio (1)-Página-9 drawio](https://user-images.githubusercontent.com/72947118/230428013-47c8532c-593c-4f86-ae6f-fdc0556a024d.png)

For each machine nodes, we create the following objects:

* Virtual Private Cloud (VPC), 
* network security groups, 
* network subnets and routing tables, gateways etc.
* machine instances corresponding to 3 nodes within the cluster. 
* In the node master config GitHub Actions, SonarCloud,Jupyter Lab

The VPC, network security groups, network subnets and routing tables ensure all cluster resources are isolated from other managed clusters.

## Usage
1-Clone the repository.

2-to use the environment modify the file download this project and modify the file [vars.tf](vars.tf), with the required Aws,git and sonarcloud variables.

3-Execute the following commands to deploy the architecture:
 * Terraform init: To start and download the required providers
 * Terraform plan: To create the architecture installation plan.
 * Terraform -auto-approve: To run the installation plan in the Aws cloud.
 * Terraform destroy: When the environment is no longer required it will delete the created infrastructure.
Please ensure you read documentation for [Terraform](https://terraform.io/docs/) and its well written [command-line interface (CLI)](https://terraform.io/docs/commands/index.html) documentation for usage.

The [terraform.tfvars](https://www.terraform.io/intro/getting-started/variables.html) in the [examples](examples/terraform.tfvars) folder is used as a variable overlay and, as per the Terraform documentation, is processed last; meaning, it overrides all command line and environment variables.  

Ensure you modify the URL on line 25 and 29 in [Installs_Cluster.tf](Installs_Cluster.tf) to reflect the correct address of your custom Spark y hadoop distribution.

It's recommended TF_VAR environment and command line variables be used as per the Terraform [documentation](https://www.terraform.io/docs/configuration/variables.html).
