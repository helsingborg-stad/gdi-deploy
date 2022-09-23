# gdi-deploy
Github action for deploying GDI microservice

This action will (optionally) set versions, build and deploy docker images for GDI microservices.

# Parameters

| Name                   | Description                                                                                   | Required |
|------------------------|-----------------------------------------------------------------------------------------------|----------|
| update-openapi-version | If the version of an OpenAPI specification should be updated                                  | false    |
| openapi-spec-file      | Path to the openapi yml specification file to update, relative to the root of the repository. | false    |
| update-package-version | If the version of package.json should be updated.                                             | false    |
| release-tag-name       | The tag that was just released                                                                | true     |
| gdi-gitops-config-repo | The repository to update configs in for a deploy                                              | true     |
| github-token           | Github token                                                                                  | true     |
| gdi-gitops-token       | GDI Gitops token                                                                              | true     |
| gdi-gitops-app         | Name of the app in the config repo                                                            | true     |
| docker-username        | Username to use when logging in to the docker registry                                        | true     |
| docker-password        | Password to use when logging in to the docker registry                                        | true     |
