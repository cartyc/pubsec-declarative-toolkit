# OCI Bootstrap

The objects in this file will be used to bootstrap an OCI deployment of the landing zone.

The following permissions will be needed to be assigned to the Config Controller Service Account

```
export PROJECT_ID=$(gcloud config list --format 'value(core.project)')
export ORG_ID=$(gcloud projects get-ancestors $PROJECT_ID --format='get(id)' | tail -1)
export SA_EMAIL="$(kubectl get ConfigConnectorContext -n config-control -o jsonpath='{.items[0].spec.googleServiceAccount}' 2> /dev/null)"
```

```
gcloud organizations add-iam-policy-binding "${ORG_ID}" --member "serviceAccount:${SA_EMAIL}" --role roles/source.admin
gcloud organizations add-iam-policy-binding "${ORG_ID}" --member "serviceAccount:${SA_EMAIL}" --role roles/cloudkms.admin
gcloud organizations add-iam-policy-binding "${ORG_ID}" --member "serviceAccount:${SA_EMAIL}" --role roles/artifactregistry.admin
gcloud organizations add-iam-policy-binding "${ORG_ID}" --member "serviceAccount:${SA_EMAIL}" --role roles/serviceusage.serviceUsageAdmin
gcloud organizations add-iam-policy-binding "${ORG_ID}" --member "serviceAccount:${SA_EMAIL}" --role roles/cloudbuild.builds.editor
```

Apply rsources to the config controller instance

```
kubectl apply -f bootstrap/
```

Commit your change to source.

```
git init --initial-branch main
git add .
git commit -m "first landing zone commit"
```