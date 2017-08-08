# Azure Key Vault (Secrets As A Service)

A scalable docker service for querying azure key vaults for secrets using service provider credentials.

## How to Install 
Git clone the repo then build the Azure KeyVault Secret Service api docker image using 

```
 docker build -t kv-service .
```

Than run the Azure KeyVault Secret Service api docker image with

```
 docker run kv-service
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
