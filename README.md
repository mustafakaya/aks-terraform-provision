# aks-terraform-provision
Create Kubernetes cluster with AKS using  Terraform

#initialize Terrafom.  
terraform init -backend-config="storage_account_name=<YourAzureStorageAccountName>" -backend-config="container_name=tfstate" -backend-config="access_key=<YourStorageAccountAccessKey>" -backend-config="key=codelab.microsoft.tfstate"

#export service principal credentials  
export TF_VAR_client_id=<service-principal-appid>  
export TF_VAR_client_secret=<service-principal-password>  

#create Terraform plan that defines the infra components  
terraform plan -out out.plan  

#apply plan to create Kubernetes cluster  
terraform apply out.plan

