# Demo Sock Shop - GitOps Implementation

This repository is designed for implementing GitOps with Azure Kubernetes Service (AKS). It contains Kubernetes manifests and a `kustomization.yaml` file to manage the deployment of the Sock Shop application.

## Setting Up GitOps with AKS

Follow these steps to configure GitOps for this repository:

1. **Create a GitOps Configuration**:
   - Navigate to your AKS cluster in the Azure portal.
   - Go to the **GitOps** section and create a new configuration.

2. **Configure the Repository**:
   - **Repository URL**: `https://github.com/fabricekrebs/demo-sockshop`
   - **Reference Type**: Branch
   - **Branch**: `master`
   - **Repository Type**: Public
   - **Sync Interval**: 2 minutes
   - **Sync Timeout**: 2 minutes

3. **Specify a Kustomization**:
   - **Instance Name**: `kustomization-1`
   - **Path**: Leave this field empty to use the root directory of the repository.

4. Save the configuration and let AKS handle the synchronization of your cluster with this repository.

## Repository Structure

- **Kubernetes Manifests**: The repository contains YAML files for deploying the Sock Shop application components.
- **Kustomization**: The `kustomization.yaml` file is used to manage and customize the deployment.

## Syncing and Updates

The GitOps configuration will automatically sync the AKS cluster with this repository every 2 minutes. Any changes pushed to the `master` branch will be applied to the cluster during the next sync.

For more information on GitOps with AKS, refer to the [Azure GitOps documentation](https://learn.microsoft.com/en-us/azure/azure-arc/kubernetes/tutorial-use-gitops-flux2).