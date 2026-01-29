# Nexus AI on Google Cloud Platform

This repository contains the deployment configuration for **Nexus AI** on Google Cloud Marketplace.

## Prerequisites

-   A Google Cloud Platform project.
-   `kubectl` installed and configured.
-   [mpdev](https://github.com/GoogleCloudPlatform/marketplace-k8s-app-tools/blob/master/docs/tool-prerequisites.md) installed (optional, for local verification).

## Deployment

### 1. Clone this repository

```bash
git clone <YOUR_PUBLIC_REPO_URL>
cd <YOUR_REPO_NAME>
```

### 2. Configure Installation parameters

View the `schema.yaml` file to understand the available parameters.
Common parameters include:
-   `name`: The release name.
-   `namespace`: The target namespace.
-   `reportingSecret`: The name of the secret containing your reporting credentials (provided by Marketplace).

### 3. Install via CLI

You can use `mpdev` to install the application:

```bash
export DEPLOYER_IMAGE=gcr.io/nexus-458211/nuklai-nexus/deployer:0.1

mpdev /scripts/install \
  --deployer=$DEPLOYER_IMAGE \
  --parameters='{"name": "nexus-ai", "namespace": "nexus-ai", "reportingSecret": "required-by-marketplace"}'
```

OR following the on-screen instructions in the Google Cloud Console.

## Support

For support, please contact support@nukl.ai.
