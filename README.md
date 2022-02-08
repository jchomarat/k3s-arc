# k3s-arc

## Links

* [Arc-enabled with k3s](https://medium.com/techbeatly/bring-your-own-kubernetes-cluster-to-azure-azure-arc-7ee7bfe3d3a6)
* [Gitops, flux v2 and arc-enabled k8s](https://docs.microsoft.com/en-us/azure/azure-arc/kubernetes/tutorial-use-gitops-flux2)

## Remarks

* with command `az connectedk8s connect --name <AzureArcName> --resource-group <ResourceGroupName> -l eastus` you can use the param `--kube-config` when no kube config
* 

## Commands

Use the command below to create a flux v2 connections

```bash
az k8s-configuration flux create -g 5g-readiness -c ubuntu-node1 -n gitops-demo --namespace 5g-readiness -t connectedClusters --scope cluster -u https://github.com/jchomarat/k3s-arc --branch main --kustomization name=apps path=./app prune=true   
```