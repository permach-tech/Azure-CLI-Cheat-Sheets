# list all user's info
```shell
az ad user list --query '[].{UserPrincipalName: userPrincipalName, DisplayName: displayName, ObjectId: objectId, Mail: mail}'
```

# list all user's usernames (userPrincipalNames in Azure)
```shell
az ad user list --query '[].userPrincipalName' --output tsv
```

# list current user's info
```shell
az ad signed-in-user show
```

# list user's role assignments
```shell
az role assignment list --all --assignee user@contoso.com --output json --query '[].{principalName:principalName, roleDefinitionName:roleDefinitionName, scope:scope}'
```

# Show a user
```shell
az ad user show --id $mail --query "displayName"
```

# create new user
```shell
az ad user create \
    --display-name "User Display Name" \
    --user-principal-name UserName@example.com \
    --password "UserPassword123!"
```

# create multiple new users, from a file
```shell
allUsers=$(cat ./user-names.txt)
for userName in $allUsers; do
    az ad user create \
        --display-name "$userName" \
        --user-principal-name "$userName@example.com" \
        --password "UserPassword123!"
done
```

# list all users
```shell
az ad user list --query '[].{UserPrincipalName: userPrincipalName, DisplayName: displayName, ObjectId: objectId, Mail: mail}' --all
```

# get a specific user's info
```shell
az ad user show \
    --id UserName@example.com
```

# delete one user
```shell
az ad user delete \
    --id UserName@example.com
```
