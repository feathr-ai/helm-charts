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

To test changes to the chart locally, run the following command from the directory /charts

```bash
helm install feathr-online ./feathr-online -f ./feathr-online/values.yaml
```
