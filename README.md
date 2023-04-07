# feathr-helm-charts

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```bash
helm repo add feathr-helm-charts https://feathr-ai.github.io/helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
feathr-online` to see the charts.

To install the feathr-online chart go to charts and run the following commands:

```bash
# Installs feathr-online
helm install <Release Name> ./feathr-online \
    --set pipelineConf=$(cat <absolute path>/pipeline.conf | base64) \
    --set lookup=$(cat <absolute path>/lookup.json | base64)

or

# Installs feathr-online with key vault integration
# Only User Assigned Identity ID is supported
helm install <Release Name> ./feathr-online-aks-integration \
    --set pipelineConf=$(cat <absolute path>/pipeline.conf | base64) \
    --set lookup=$(cat <absolute path>/lookup.json | base64) \
    --set userAssignedIdentityID=<User Assigned Identity ID> \
    --set tenantId=<Tenant ID>
```

**The `feathr-online` pod is install in `<Release Name>` namespace.**

Here we have two helm charts:
1. `feathr-online`: To install only `fethr-online`
1. `feathr-online-aks-integration`: To install only `fethr-online` with Azure Key Vault Plugin

To uninstall the chart:

```bash
helm uninstall <Release Name>
```

## Local Development

To test changes to the chart locally with dry run, run the following command from helm-charts

```bash
helm install <Release Name> ./feathr-online \
    --set pipelineConf=$(cat <absolute path>/pipeline.conf | base64) \
    --set lookup=$(cat <absolute path>/lookup.json | base64) \
    --dry-run
```

## AKS Connection

**Instructions**

1. Open Cloud Shell or the Azure CLI
1. Run the following commands
```bash
az account set --subscription <SUBSCRIPTION ID>
```
1. Get the credentials
```bash
az aks get-credentials --resource-group <RESOURCE GROUP> --name <AKS CLUSTER NAME>
```

Once the correct credentials have been set correctly, please follow the instructions above.
