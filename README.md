# Terraform file to create automated backup of Azure VMs

This repository contains a Terraform module for creating a basic Azure infrastructure with a virtual network, subnet, storage account, network interface, virtual machine, recovery services vault, backup policy, and a protected VM for backup.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- Terraform installed on your machine.
- An Azure subscription and credentials.

## Usage

1. Initialize Terraform:
```
terraform init
```
2. Create a `terraform.tfvars` file to provide values for the required variables.

3. Plan the Terraform deployment to see the changes:
```
terraform plan
```
4. Apply the changes to create the infrastructure:
```
terraform apply
```
## Resources Created

- **Resource Group**: A resource group named `shubham-rg` located in `West US`.
- **Virtual Network**: A virtual network named `my-virtual-network` with an address space of `10.0.0.0/16`.
- **Subnet**: A subnet named `new-subnet` within the virtual network with an address prefix of `10.0.0.0/18`.
- **Network Interface**: A network interface named `nic-01` with dynamic private IP allocation.
- **Virtual Machine**: An Ubuntu Server 16.04 LTS virtual machine named `my-vm` with a size of `Standard_DS1_v2`.
- **Recovery Services Vault**: A recovery services vault named `tfex-recovery-vault` for managing backups.
- **Backup Policy**: A backup policy named `tfex-recovery-vault-policy` with daily, weekly, monthly, and yearly retention rules.
- **Backup Protected VM**: A backup protection for the virtual machine using the created backup policy.

## Outputs

After successful deployment, the following outputs will be available:
- Azure VM's public IP address.
- Connection details for the virtual machine.
- Recovery services vault details.
