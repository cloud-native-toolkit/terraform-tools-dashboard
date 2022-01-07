# Developer Dashboard terraform module

![Verify and release module](https://github.com/ibm-garage-cloud/terraform-tools-dashboard/workflows/Verify%20and%20release%20module/badge.svg)

Installs the Cloud-Native Toolkit Developer Dashboard into the cluster.

## Supported platforms

This module supports the following Kubernetes distros

- Kubernetes 1.17+
- OCP 4.3+

## Module dependencies

- Cluster
- Namespace

## Software dependencies

- kubectl
- helm terraform provider (provided by the terraform infrastructure)

## Example usage

```hcl-terraform
module "dev_tools_dashboard" {
  source = "github.com/ibm-garage-cloud/teraform-tools-dashboard.git"

  cluster_ingress_hostname = module.dev_cluster.platform.ingress
  cluster_config_file      = module.dev_cluster.config_file_path
  cluster_type             = module.dev_cluster.platform.type_code
  tls_secret_name          = module.dev_cluster.platform.tls_secret
  releases_namespace       = module.dev_capture_state.namespace
}
```
