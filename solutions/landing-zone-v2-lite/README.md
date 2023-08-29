# Landing Zone v2 Lite Install

## Description

This package is an opinionated, prepackaged and versioned implementation of Landing Zone v2 designed to quickly get a Google Cloud Landing Zone up and running. 

This is optimized for use by teams that do not need isolated landing zones per client/workgroup/teams, if that is the case then the standard Landing Zone v2 [installation](../../docs/landing-zone-v2/README.md) would be a best choice or if you require a higher degree of flexibility.

The following packages are installed as part of this deployment.

- [Gatekeeper-Policies](../gatekeeper-policies/) v0.2.0
- [Core-Landing-Zone](../core-landing-zone/) v0.3.1
- [client-landing-zone](../client-landing-zone/) v0.4.2 x3 (dev, preprod, prod envs)
- [client-setup](../client-setup/) v0.4.1 x3 (dev, preprod, prod envs)


### What gets provisioned?

The same resources as described in the Landing Zone v2 [readme](../../docs/landing-zone-v2/README.md#folder-structure-per-environment-dev-preprod-prod) will be provisioned. The main difference is that under the `clients` directory we provision a `dev`, `preprod` and `prod` environment instead of a client centric one.

## Usage

```shell
kpt pkg get https://github.com/GoogleCloudPlatform/pubsec-declarative-toolkit.git/solutions/landing-zone-v2-lite@<version>
```

### Fetch the package
`kpt pkg get REPO_URI[.git]/PKG_PATH[@VERSION] landing-zone-v2-mono`
Details: https://kpt.dev/reference/cli/pkg/get/

### View package content
`kpt pkg tree landing-zone-v2-mono`
Details: https://kpt.dev/reference/cli/pkg/tree/

### Apply the package
```
kpt live init landing-zone-v2-mono
kpt live apply landing-zone-v2-mono --reconcile-timeout=2m --output=table
```
Details: https://kpt.dev/reference/cli/live/
