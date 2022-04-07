# hippa-tenant

This is an abstract tenant package that has following capabilities enabled by default:

- service-mesh capabilities
- hippa-compliance

## Description
This package is an abstract package created from another upstream package
`service-mesh-tenant` with the following customizations:

- Enable service mesh for this tenant
`kpt fn eval . --image set-labels:v0.1.5 --match-kind=Namespace -- hippa-compliance=true`

## Usage

### Fetch the package
`kpt pkg get REPO_URI[.git]/PKG_PATH[@VERSION] base-tenant`
Details: https://kpt.dev/reference/cli/pkg/get/

### View package content
`kpt pkg tree base-tenant`
Details: https://kpt.dev/reference/cli/pkg/tree/

### Apply the package
```
kpt live init base-tenant
kpt live apply base-tenant --reconcile-timeout=2m --output=table
```
Details: https://kpt.dev/reference/cli/live/
