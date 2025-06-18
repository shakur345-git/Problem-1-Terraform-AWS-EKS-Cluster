Here's a quick step-by-step to provision the EKS cluster using Terraform:

1. **Set Up the Project Folder**  
   Organize `.tf` files—include `main.tf`, `variables.tf`, `outputs.tf`, etc.

2. **Define the AWS Provider**  
   In `providers.tf`, configure the AWS provider and specify your region.

3. **Set Versions and Requirements**  
   Use `versions.tf` to specify Terraform and provider versions (AWS, Kubernetes).

4. **Create a VPC with Subnets**  
   In `vpc.tf`, use the [official VPC module](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws) to set up public/private subnets.

5. **Deploy EKS**  
   In `eks.tf`, use the [terraform-aws-modules/eks](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws) module. Define your cluster and set up 2 `t3.medium` worker nodes.

6. **Declare Outputs**  
   In `outputs.tf`, export the cluster endpoint and kubeconfig values.

7. **Run the Commands**  
  
   terraform init
   
   terraform plan
   
   terraform apply
   

9. **Validate with kubectl**  
   After apply, configure access:
   
   Command: aws eks --region <region> update-kubeconfig --name <cluster_name>

   Command: kubectl get nodes
   
