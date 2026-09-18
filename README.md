# gha-aks-admin-login

Composite action: Azure OIDC login (via [gha-azure-login](https://github.com/alderichoarau/gha-azure-login)) +
admin kubeconfig for a given AKS cluster. Trainer-only tooling — app deploy workflows use a
namespace-scoped identity instead.

```yaml
- uses: alderichoarau/gha-aks-admin-login@v1
  with:
    client-id: ${{ secrets.AZURE_CLIENT_ID }}
    tenant-id: ${{ secrets.AZURE_TENANT_ID }}
    subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
    resource-group: rg-shared-prf2026
    cluster-name: aks-nonprod-prf2026
```

## Versioning

Tags are bare `vN`, immutable, never moved -- native Dependabot `github-actions` updates work.
Release a new version: run **"Tag a new version"** (manual dispatch) -- only after an actual
change to this repo's content. Running it again with nothing new since the last tag is refused
by the workflow (it would just create a duplicate tag pointing at the same commit).
