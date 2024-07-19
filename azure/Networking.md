
# Create a virtual network:
    ```shell
    az network vnet create --name <vnet-name> --resource-group <resource-group-name> --location <location> --address-prefix <address-prefix>
    ```

# Create a subnet within a virtual network:
    ```shell
    az network vnet subnet create --name <subnet-name> --vnet-name <vnet-name> --resource-group <resource-group-name> --address-prefix <subnet-address-prefix>
    ```

# Create a network security group:
    ```shell
    az network nsg create --name <nsg-name> --resource-group <resource-group-name> --location <location>
    ```

# Create a network security group rule:
    ```shell
    az network nsg rule create --name <rule-name> --nsg-name <nsg-name> --resource-group <resource-group-name> --priority <priority> --protocol <protocol> --source-address-prefix <source-address-prefix> --destination-address-prefix <destination-address-prefix> --access <access> --direction <direction>
    ```

# Create a public IP address:
    ```shell
    az network public-ip create --name <public-ip-name> --resource-group <resource-group-name> --location <location> --allocation-method <allocation-method>
    ```

# Create a network interface:
    ```shell
    az network nic create --name <nic-name> --resource-group <resource-group-name> --location <location> --subnet <subnet-id> --public-ip-address <public-ip-id>
    ```

# Create a virtual machine:
    ```shell
    az vm create --name <vm-name> --resource-group <resource-group-name> --location <location> --image <image-name> --admin-username <admin-username> --admin-password <admin-password> --nics <nic-id>
    ```

# Create a virtual network gateway:
    ```shell
    az network vnet-gateway create --name <gateway-name> --resource-group <resource-group-name> --location <location> --vnet <vnet-id> --public-ip-address <public-ip-id> --gateway-type <gateway-type> --sku <gateway-sku>
    ```