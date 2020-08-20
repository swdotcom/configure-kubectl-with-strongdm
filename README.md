# Configure kubectl with StrongDM Action

Composite Github action to configure kubectl using the StrongDM CLI

This requires the use of a StrongDM service account token with access to a kubernetes cluster.

<https://www.strongdm.com/docs/admin-guide/service-accounts/>

Make sure the service account is setup to auto connect to all data sources as described in the StrongDM documentation.

The workflow runner you are using must have kubectl installed. All of Github's hosted runner, except for MacOS, already have kubectl installed. The MacOS image has homebrew, so it can easily be installed that way.

<https://docs.github.com/en/actions/reference/software-installed-on-github-hosted-runners>

# Usage

See [action.yml](action.yml)

## Example usage

```yaml
uses: swdotcom/configure-kubectl-with-strongdm@v1
with:
  sdm-admin-token: ${{ secrets.SDM_ADMIN_TOKEN }}
```
