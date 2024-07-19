# List storage accounts
```shell
az storage account list
```

# List all storage accounts by name only
```shell
az storage account list --query "[].{name:name}" --output tsv
```

# List all storage accounts in a resource group.
```shell
az storage account list -g MyResourceGroup
```

# create a general-purpose v2 storage account with read access LRS
az storage account create \
```shell
--name test-sa-v2-persell \
--resource-group test-rg-persellmach \
--location southcentralus \
--sku Standard_LRS \
--kind StorageV2 \
--min-tls-version TLS1_2 \
--allow-blob-public-access false
```

# Delete a storage account
```shell
az storage account delete --name <storage-account-name> --resource-group <resource-group-name>
```

# upload file to blob storage using SAS Token (Must have Azure CLI installed locally)
```shell
az storage blob upload \
    --account-name mystorageaccount \
    --sas-token <your-sas-token> \
    --container-name mycontainer \
    --name example.txt \
    --file /path/to/example.txt
```
