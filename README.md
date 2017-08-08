# Azure Key Vault (Secrets As A Service)

A scalable docker service for querying azure key vaults for secrets using Azure Service Provider Credentials.

## How to Install 

1. Clone the "azure-key-vault-secret-as-a-service" repo
```
git clone https://github.com/CatalystCode/azure-key-vault-secret-as-a-service.git
```
2. Add Service Provider Credentials To Dockerfile.
```
ENV AZURE_TENANT_ID {PUT_AZURE_TENANT_ID_HERE}
ENV AZURE_CLIENT_ID {PUT_AZURE_CLIENT_ID_HERE}
ENV AZURE_CLIENT_SECRET {PUT_AZURE_CLIENT_SECRET_HERE}
ENV AZURE_SUBSCRIPTION_ID {PUT_AZURE_SUBSCRIPTION_ID_HERE}
```
2. Build the Azure KeyVault Secret Service api docker image using 

```
 docker build -t kv-service .
```
Or retrieve the image from dockerhub from the "" endpoint

3. Run the Azure KeyVault Secret Service api docker image with the correct service provider credentials

```
docker run -e AZURE_TENANT_ID='azure_tenant_id' -e AZURE_CLIENT_ID='azure_client_id' -e AZURE_CLIENT_SECRET='azure_client_secret' -e AZURE_SUBSCRIPTION_ID='azure_subscription_id' kv-service
```

## How to Use 

Once the container is running to use the Azure KeyVault Secret Service api you can choose to retrieve a secret from a vault with the following command in the docker terminal:
```
python AzureKeyVaultSecretService.py Get_Secret {Vault_Name} {Secret_Name} 
```
Or search all vaults for a secret with:

```
python AzureKeyVaultSecretService.py Search_Secret {Secret_Name}
```
