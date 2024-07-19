az storage account create \
--name test-sa-v2-persell \
--resource-group test-rg-persellmach \
--location southcentralus \
--sku Standard_LRS \
--kind StorageV2 \
--min-tls-version TLS1_2 \
--allow-blob-public-access false