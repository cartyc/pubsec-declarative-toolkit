# azure-lz

## Description
sample description

## Usage

### Fetch the package
`kpt pkg get REPO_URI[.git]/PKG_PATH[@VERSION] azure-lz`
Details: https://kpt.dev/reference/cli/pkg/get/

### View package content
`kpt pkg tree azure-lz`
Details: https://kpt.dev/reference/cli/pkg/tree/

### Apply the package
```
kpt live init azure-lz
kpt live apply azure-lz --reconcile-timeout=2m --output=table
```
Details: https://kpt.dev/reference/cli/live/
