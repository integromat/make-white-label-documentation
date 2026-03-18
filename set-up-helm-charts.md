# Set up Helm charts

This guide outlines the steps required to set up and deploy Helm charts for your **On-premise** services.

## Set up the Helm charts

To set up the Helm charts, follow the process below:

1. [Install Helm](set-up-helm-charts.md#install-helm)
2. [Create a Personal Access Token](set-up-helm-charts.md#create-a-personal-access-token)
3. [Authenticate with GitHub Container Registry](set-up-helm-charts.md#authenticate-with-github-container-registry-using-docker)
4. [Update Helm Dependencies](set-up-helm-charts.md#update-helm-dependencies)

### Install Helm

To install Helm, refer to the [Installing Helm documentation](https://helm.sh/docs/intro/install/) and follow the outlined steps.

### Create a Personal Access Token

To authenticate with GitHub's container registry and pull charts from the OCI registry, you first need to create a Personal Access Token (PAT). To generate your token:

1. Log in to your GitHub account.
2. In the upper-right corner, click your **Profile photo** > **Settings**.
3. In the left sidebar, click **Developer Settings**.
4. Click **Personal access tokens** > **Tokens (classic)**.
5. Click **Generate new token (classic)**.
6. Enter a **Note** for the token.
7. In the **Select scopes** field, enable the `read:packages` permission.
8. Click **Generate token**.
9. Copy the **Personal access tokens (classic)** value and store it in a safe place.

You will use this token to authenticate with Docker in the section below.

### Authenticate with GitHub Container Registry using Docker

To authenticate with the GitHub Container Registry using Docker and gain access to pull Helm charts:

1. Run the following command. Ensure `$GITHUB_TOKEN` is set to your Personal Access Token and `$GITHUB_USER` is set to your GitHub username:

```bash
echo $GITHUB_TOKEN | docker login ghcr.io -u $GITHUB_USER --password-stdin
```

2. Enter your GitHub username and the Personal Access Token when prompted.

Once authenticated, you can pull Helm charts from the GitHub OCI registry.

### Update Helm dependencies

To download all required chart dependencies before installation, navigate to the directory where your Helm Chart is located and run the following:

```
helm dependency update
```

This downloads all required chart dependencies.

You’ve successfully completed the setup to deploy Helm charts for your On-premise services.
