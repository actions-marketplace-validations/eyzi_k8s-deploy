# k8s-deploy

update image of kubernetes deployment through API

## Usage

```yml
- uses: eyzi/k8s-deploy@v1
  with:
    api_url: https://example.com/apis/apps/v1/namespaces/default/deployments/sample-app
    api_token: example.Bearer.Token
    image: sample-image
    version: 1.0.0
```

- `api_url` (required) - kubernetes API url of the deployment

- `api_token` (required) - a jsonwebtoken with access to deployment.
  the easiest way to create one is by creating a `ServiceAccount` with
  `Role` that has permission to update the deployments

- `image` (required) - this image will replace the current image of the
  deployment

- `version` (required) - image version to deploy
