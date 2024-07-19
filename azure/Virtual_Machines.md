
Create a virtual machine:
    ```
    az vm create --name <vm_name> --resource-group <resource_group_name> --image <image_name> --admin-username <admin_username> --admin-password <admin_password> --size <vm_size>
    ```

Start a virtual machine:
    ```
    az vm start --name <vm_name> --resource-group <resource_group_name>
    ```

Stop a virtual machine:
    ```
    az vm stop --name <vm_name> --resource-group <resource_group_name>
    ```

Restart a virtual machine:
    ```
    az vm restart --name <vm_name> --resource-group <resource_group_name>
    ```

Delete a virtual machine:
    ```
    az vm delete --name <vm_name> --resource-group <resource_group_name> --yes
    ```

List all virtual machines in a resource group:
    ```
    az vm list --resource-group <resource_group_name>
    ```

Create a managed disk:
    ```
    az disk create --name <disk_name> --resource-group <resource_group_name> --size-gb <disk_size> --sku <disk_sku>
    ```

Attach a disk to a virtual machine:
    ```
    az vm disk attach --vm-name <vm_name> --resource-group <resource_group_name> --disk <disk_name> --lun <lun_number>
    ```

Detach a disk from a virtual machine:
    ```
    az vm disk detach --vm-name <vm_name> --resource-group <resource_group_name> --disk <disk_name>
    ```

Delete a disk:
     ```
     az disk delete --name <disk_name> --resource-group <resource_group_name> --yes
     ```