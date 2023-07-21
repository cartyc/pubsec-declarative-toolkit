# landing-zone-v2-mono

## Description
Mono-Repo LZ. Contains the following packages
- Gatekeeper-Policies
- Core-Landing-Zone

## Usage

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
