# Vault Helm Chart

> :warning: **Please note**: We take Vault's security and our users' trust very seriously. If 
you believe you have found a security issue in Vault Helm, _please responsibly disclose_ 
by contacting us at [security@hashicorp.com](mailto:security@hashicorp.com).

This repository contains the official HashiCorp Helm chart for installing
and configuring Vault on Kubernetes. This chart supports multiple use
cases of Vault on Kubernetes depending on the values provided.

For full documentation on this Helm chart along with all the ways you can
use Vault with Kubernetes, please see the
[Vault and Kubernetes documentation](https://www.vaultproject.io/docs/platform/k8s/).

## Prerequisites

To use the charts here, [Helm](https://helm.sh/) must be configured for your
Kubernetes cluster. Setting up Kubernetes and Helm is outside the scope of
this README. Please refer to the Kubernetes and Helm documentation.

The versions required are:

  * **Helm 3.0+** - This is the earliest version of Helm tested. It is possible
    it works with earlier versions but this chart is untested for those versions.
  * **Kubernetes 1.9+** - This is the earliest version of Kubernetes tested.
    It is possible that this chart works with earlier versions but it is
    untested. Other versions verified are Kubernetes 1.10, 1.11.

## Usage

To install the latest version of this chart, add the Hashicorp helm repository
and run `helm install`:

```console
helm install --namespace infra-services central-vault ./Vault
```

Please see the many options supported in the `values.yaml` file. These are also
fully documented directly on the [Vault
website](https://www.vaultproject.io/docs/platform/k8s/helm) along with more
detailed installation instructions.

## unseal vault
```
curl --header "content-type: application/json" --request PUT --data '{"key":"YviKu0R2eIMt8mCopZiq4XO9DaIjm3xDEuuFwSnA0KU="}' https://central-vault.ecc-dev.progressoft.cloud/v1/sys/unseal
```

## Add Key usin curl command:
```
curl --header 'X-Vault-Token: s.dDrIn2JyYwgfWXP1UyZe0imm' --request POST --data ' {"password": "my-long-password" , "username" : "awad" }' --insecure https://central-vault.ecc-dev.progressoft.cloud/v1/awad/V3
```

## Vault keys:
```json
{
  "keys": [
    "62f88abb447678832df260a8a598aae173bd0da2239b7c4312eb85c129c0d0a5"
  ],
  "keys_base64": [
    "YviKu0R2eIMt8mCopZiq4XO9DaIjm3xDEuuFwSnA0KU="
  ],
  "root_token": "s.dDrIn2JyYwgfWXP1UyZe0imm"
}
```