# Problem-1-Terraform-AWS-EKS-Cluster

## Run Instructions

1. Initialize: `terraform init`
2. Plan: `terraform plan`
3. Apply: `terraform apply`
4. Configure kubectl:

vpc.tf – Use terraform-aws-modules/vpc/aws module for fast setup.
eks.tf – Use terraform-aws-modules/eks/aws:

aws eks --region <region> update-kubeconfig --name <cluster_name> kubectl get nodes
