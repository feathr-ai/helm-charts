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

To install the feathr-online chart:

```bash
helm install feathr-online feathr-helm-charts/feathr-online
```

To uninstall the chart:

```bash
helm delete feathr-online
```

## Local Development

To test changes to the chart locally, run the following command from helm-charts

```bash
helm install feathr-online ./charts/feathr-online -f ./charts/feathr-online/values.yaml
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
