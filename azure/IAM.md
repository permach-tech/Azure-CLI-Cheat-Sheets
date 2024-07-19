# list all user's info
az ad user list --query '[].{UserPrincipalName: userPrincipalName, DisplayName: displayName, ObjectId: objectId, Mail: mail}'

# list all user's usernames (userPrincipalNames in Azure)
az ad user list --query '[].userPrincipalName' --output tsv

# list current user's info
az ad signed-in-user show

# list user's role assignments
az role assignment list --all --assignee user@contoso.com --output json --query '[].{principalName:principalName, roleDefinitionName:roleDefinitionName, scope:scope}'

# Show a user
az ad user show --id $mail --query "displayName"

# create new user
az ad user create \
    --display-name "User Display Name" \
    --user-principal-name UserName@example.com \
    --password "UserPassword123!"

# create multiple new users, from a file
allUsers=$(cat ./user-names.txt)
for userName in $allUsers; do
    az ad user create \
        --display-name "$userName" \
        --user-principal-name "$userName@example.com" \
        --password "UserPassword123!"
done

# list all users
az ad user list --query '[].{UserPrincipalName: userPrincipalName, DisplayName: displayName, ObjectId: objectId, Mail: mail}' --all

# get a specific user's info
az ad user show \
    --id UserName@example.com

# delete one user
az ad user delete \
    --id UserName@example.com
