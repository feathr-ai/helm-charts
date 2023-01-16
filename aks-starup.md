# AKS Connection

## Usage

1. Open Cloud Shell or the Azure CLI
1. Run the following commands
```bash
az account set --subscription <SUBSCRIPTION ID>
```
1. Get the credentials
```bash
az aks get-credentials --resource-group <RESOURCE GROUP> --name <AKS CLUSTER NAME>
```

Once the correct credentials have been set correctly, please follow the instructions in [README](https://github.com/feathr-ai/helm-charts/blob/main/README.md).
