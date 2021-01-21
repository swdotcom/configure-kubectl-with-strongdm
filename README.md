# Configure kubectl with StrongDM Action

Composite Github action to configure kubectl using the StrongDM CLI

This requires the use of a StrongDM service account token with access to a kubernetes cluster.

<https://www.strongdm.com/docs/admin-guide/service-accounts/>

Make sure the service account is setup to auto connect to all data sources as described in the StrongDM documentation.

The workflow runner you are using must have kubectl installed. All of Github's hosted runner, except for MacOS, already have kubectl installed. The MacOS image has homebrew, so it can easily be installed that way.

<https://docs.github.com/en/actions/reference/software-installed-on-github-hosted-runners>

# Usage

See [action.yaml](action.yaml)

## Example usage

```yaml
- name: Configure Kubectl with StrongDM
  uses: swdotcom/configure-kubectl-with-strongdm@v1
  with:
    sdm-admin-token: ${{ secrets.SDM_ADMIN_TOKEN }}
```

If you're having issues with the action successfully completing, then StrongDM may have bumped your organization to a later release of the CLI.

> Thanks for contacting Support! I'd be happy to help with the question. Behind the scenes, strongDM has a progressive sequence of release channels; on occasion, we may need to accelerate a fix or enhancement to your organization.
>
> The additional string is optional, and handles the cases where a custom or early release build has been configured for use in your organization. With the string omitted, you will always receive the "stable" build.

To use your organizations CLI version then set the appropriate download URL. You can find your URL [here](https://app.strongdm.com/app/download).

```yaml
- name: Configure Kubectl with StrongDM
  uses: swdotcom/configure-kubectl-with-strongdm@v1
  with:
    sdm-admin-token: ${{ secrets.SDM_ADMIN_TOKEN }}
    sdm-download-url: https://app.strongdm.com/releases/cli/linux/<organization name>
```
