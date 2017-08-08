# Azure Key Vault (Secrets As A Service)

A scalable docker service for querying azure key vaults for secrets using Azure Service Provider Credentials.


## How to Use 

Once the container is running to use the Azure KeyVault Secret Service api you can choose to retrieve a secret from a vault with the following command in the docker terminal:
```
docker run --rm -e AZURE_TENANT_ID='azure_tenant_id' -e AZURE_CLIENT_ID='azure_client_id' -e AZURE_CLIENT_SECRET='azure_client_secret' -e AZURE_SUBSCRIPTION_ID='azure_subscription_id' catalystcode/azure-key-vault-secret-as-a-service python AzureKeyVaultSecretService.py Get_Secret {Vault_Name} {Secret_Name} 
```
Or search all vaults for a secret with:

```
docker run --rm -e AZURE_TENANT_ID='azure_tenant_id' -e AZURE_CLIENT_ID='azure_client_id' -e AZURE_CLIENT_SECRET='azure_client_secret' -e AZURE_SUBSCRIPTION_ID='azure_subscription_id' catalystcode/azure-key-vault-secret-as-a-service python AzureKeyVaultSecretService.py Search_Secret {Secret_Name}
```
