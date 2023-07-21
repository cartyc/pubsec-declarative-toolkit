# kpt Landing Zone installation

## Gatekeeper

1. Fetch the gatekeeper package. This package contains policies that will be enforced on your infrastructure.

   ```bash
   kpt pkg get https://github.com/GoogleCloudPlatform/pubsec-declarative-toolkit.git/solutions/gatekeeper-policies@<VERSION>
   ```

2. Modify the `setters.yaml` file with the appropriate data.

3. Initialize the package and deploy it.

   ```
   kpt live init
   kpt live apply
   ```

## Core Landing Zone

1. Fetch the Package

   ```bash
   kpt pkg get https://github.com/GoogleCloudPlatform/pubsec-declarative-toolkit.git/solutions/core-landing-zone@<VERSION>
   ```

2. Modify the `setters.yaml` file with the appropriate data.

3. Initialize the package and deploy it.

   ```bash
   kpt live init
   kpt live apply
   ```

## Client Setup

0. Create client directory
   
   ```bash
   mkdir clients
   ```

1. Fetch the Package

   ```bash
   kpt pkg get https://github.com/GoogleCloudPlatform/pubsec-declarative-toolkit.git/solutions/client-setup@<VERSION> ./clients/<client name>
   ```

2. Modify the `setters.yaml` file with the appropriate data.

3. Initialize the package and deploy it.

   ```bash
   kpt live init
   kpt live apply
   ```

## Client Landing Zone

```bash
kpt live init
kpt live apply
```

## Client Project

```bash
kpt live init
kpt live apply
```