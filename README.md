<p>
  <a href="https://github.com/helsingborg-stad/gdi-k8s-config">
    <img src="docs/images/hbg-github-logo-combo.png" alt="Logo" width="300">
  </a>
</p>
<h1>GDI Deploy</h1>
<p>
  Github action for deploying GDI microservice
</p>

# Summary
This action will (optionally) set versions, build and deploy docker images for GDI microservices.

The v1 action requires GitHub Actions Runner v2.327.1 or later because its JavaScript actions use the Node.js 24 runtime.

# Parameters

| Name                   | Description                                                                                   | Required |
|------------------------|-----------------------------------------------------------------------------------------------|----------|
| update-openapi-version | If the version of an OpenAPI specification should be updated                                  | false    |
| openapi-spec-file      | Path to the openapi yml specification file to update, relative to the root of the repository. | false    |
| update-package-version | If the version of package.json should be updated.                                             | false    |
| release-tag-name       | The tag that was just released                                                                | true     |
| gdi-gitops-config-repo | The repository to update configs in for a deploy                                              | true     |
| github-token           | Github token, with `write:package`, `read:package` and`repo:*` scopes                         | true     |
| gdi-gitops-token       | GDI Gitops token                                                                              | true     |
| gdi-gitops-app         | Name of the app in the config repo                                                            | true     |
| gdi-gitops-env         | Name of the overlay to update in the config repo                                              | true     |
| docker-username        | Username to use when logging in to the docker registry                                        | true     |
| docker-password        | Password to use when logging in to the docker registry                                        | true     |

For v1 compatibility, `github-token` is also passed to Docker builds as the `GITHUB_ACCESS_TOKEN` build argument. Dockerfiles must not print it or persist it in an image layer; migrating this interface to a BuildKit secret requires a new major version.
