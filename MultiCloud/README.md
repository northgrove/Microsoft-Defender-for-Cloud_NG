# Terraform onboarding for Micorsoft Defender for Cloud

Welcome to Terraform onboarding for Micorsoft Defender for Cloud

## Creating resources in the destination cloud

To create the necessary resources (like roles) in AWS/GCP, perform the following actions:

* Clone the relevant cloud folder with the terraform template 

```
Templates --> GCP --> Local
```

* Create variables file (.tfvars) containing the needed variable 

``` 
project_id = 123456789
workload pool id is the tenant id on Azure workload_pool_id
```

* Run terraform commands to deploy

```
terraform init terraform plan -var-file=cloud_vars.tfvars terraform apply -var-file=cloud_vard.tfvars
```

## Creating the security connector in Azure

To create the security connector in Azure, perform the following actions:

* Clone the MultipleAccount folder
* Create variables file (.tfvars) containing the needed variable 

``` 
account_id_or_project_number = ["123415589123", "12343123123"] 
gcp_project_names = ["project_example1", "project_example2"] 
mdc_azure_resource_group_name = "rg_gcp_corp_projects" 
mdc_azure_resource_group_prefix = ["first", "second"] 
mdc_azure_resource_group_location = "westeurope" 
mdc_cloud_type = "GCP"
```

* Run terraform commands to deploy 

```
terraform init terraform plan -var-file=cloud_vars.tfvars terraform apply -var-file=cloud_vard.tfvars
```