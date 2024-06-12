# CD-CustomDeploy

CD-CustomDeploy is an automated scripting system developed to facilitate the deployment of infrastructure on AWS Cloud. Leveraging Terraform and bash scripts, this project allows users to specify custom configurations for their AWS resources, providing a flexible and efficient solution for infrastructure management.

## Features

- **Interactive Interface:** Prompts the user for configuration preferences, including hardware type, AWS region, number of instances, and S3 bucket name.
- **Full Automation:** From Terraform initialization to infrastructure application and destruction, the entire process is fully automated.
- **Secure Credential Storage:** AWS credentials are securely stored in a Terraform variables file (credentials.tfvars).
- **S3 Bucket Management:** Verifies the existence of S3 buckets and safely deletes objects before destroying the infrastructure.
- **Customizable Configurations:** Allows the selection of specific hardware features, EC2 instance names, and other relevant parameters for the infrastructure.

## Requirements

- Terraform
- AWS CLI
- Bash

## Installation

Clone the repository:

git clone https://github.com/your-username/CD-CustomDeploy.git
cd CD-CustomDeploy

Ensure you have the necessary tools installed (Terraform, AWS CLI, and Bash).

## Usage
Run the consola.sh script to start the configuration process:

```bash
./consola.sh
```

Follow the instructions to provide your desired configuration.

You can enter AWS Access Key ID and Secret Access Key in two ways:

Directly in the command line when running consola.sh with the -c option:

```bash
./consola.sh -c
```

Or manually create a credentials.tfvars file in the terraform_configuration directory with the following content:

```bash
access_key = "your-access-key-id"
secret_key = "your-secret-access-key"
```

Once the configuration is complete, the scripts will automate the initialization, application, and deployment of the infrastructure on AWS.

To destroy the infrastructure and clean up resources, run:

```bash
./eliminar.sh
```

## Important Files
consola.sh: Main script to interact with the user and gather desired configurations.
inicializar.sh: Script to read configurations from config.txt and set necessary environment variables.
ejecutar.sh: Script to execute Terraform commands to deploy the infrastructure.
eliminar.sh: Script to destroy the infrastructure and clean up resources on AWS.
config.txt: File generated with user-selected configurations.
credentials.tfvars: File generated to store AWS credentials (if using the -c option in consola.sh).

## Contribution
Contributions are welcome! If you wish to improve this project, please open an issue or send a pull request.

## License
This project is licensed under the MIT License.
