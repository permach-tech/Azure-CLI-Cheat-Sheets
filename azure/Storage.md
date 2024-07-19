# List storage accounts
az storage account list

# List all storage accounts by name only
az storage account list --query "[].{name:name}" --output tsv

# List all storage accounts in a resource group.
az storage account list -g MyResourceGroup

# create a general-purpose v2 storage account with read access LRS
az storage account create \
  --name your-sa-name-here \
  --resource-group your-rg-name-here \
  --location southcentralus \
  --sku Standard_LRS \
  --kind StorageV2 \
  --min-tls-version TLS1_2 \
  --allow-blob-public-access false

# Delete a storage account
az storage account delete --name <storage-account-name> --resource-group <resource-group-name>

# upload file to blob storage using SAS Token (Must have Azure CLI installed locally)
az storage blob upload \
    --account-name mystorageaccount \
    --sas-token <your-sas-token> \
    --container-name mycontainer \
    --name example.txt \
    --file /path/to/example.txt

