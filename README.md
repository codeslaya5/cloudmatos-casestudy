# Remediation Case Study
## Remediation Use Case Problem Statement
EKS control plane logging is enabled for your Amazon EKS clusters

## Why remediation?
By default, cluster control plane logs aren't sent to CloudWatch Logs. Hence, we must enable each log type individually to provide audit and diagnostic logs directly from the Amazon EKS control plane to CloudWatch Logs. These logs can help you to secure and efficiently run your EKS clusters. You can select the exact log types you need, and the logging data is sent as log streams to the AWS CloudWatch log group created for the specified Amazon EKS cluster.

## Remediation steps
- Initialize the Terraform working directory with the help of an Ansible Playbook script
- Create a task with a conditional that is triggered when control plane logging is disabled
- If control plane logging is disabled, the terraform plan is terminated
- Enable control logging in aws_eks_cluster resource to faciliate successful deployment of AWS EKS

## How to setup infrastructure for testing?
- Make sure you have a valid AWS account
- Terraform and Ansible should be installed on your local machine/VM

## How to run the script?
- Use the command 'ansible-playbook playbook.yml' in the terminal to execute the Ansible Playbook script
- If you wish to run your playbook against specific hosts, create an inventory file and run 'ansible-playbook -i <path_to_inventory_file> playbook.yml'

## Details about the variables or parameters used
- The terraform working directory comprises EKS cluster and worker nodes, security groups, VPCs, and subnet variables
- The playbook.yml uses Ansible's terraform module to execute the terraform working directory

## Details of files and folders
- The 'terraform' folder represents the entire terraform working directory for AWS EKS
- playbook.yml is the Ansible Playbook script
