# Artifacts Tagger

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [How To Use](#how-to-use)
- [Support](#support)

## Overview

The **Artifacts Tagger** [extension](https://marketplace.visualstudio.com/items?itemName=dmitryserbin.artifacts-tagger) adds a task to Azure DevOps to tag all build artifacts in a classic release pipeline or tag current build in a classic build pipeline.

Extension | Build | Code
:-------|:-------|:-------
[![Extension](https://vsmarketplacebadge.apphb.com/version/dmitryserbin.artifacts-tagger.svg)](https://marketplace.visualstudio.com/items?itemName=dmitryserbin.artifacts-tagger) | [![Build](https://dev.azure.com/dmitryserbin/Tagger/_apis/build/status/Tagger-master)](https://dev.azure.com/dmitryserbin/Tagger/_build/latest?definitionId=1) | [![CodeFactor](https://www.codefactor.io/repository/github/dmitryserbin/azdev-artifacts-tagger/badge)](https://www.codefactor.io/repository/github/dmitryserbin/azdev-artifacts-tagger)

## Features

The **Artifacts Tagger** task adds various [default](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/variables?view=azure-devops) or user-defined tags to all build artifacts in a classic release pipeline or current build in a classic build pipeline.

It uses either **integrated** or **user-defined**  personal access token (PAT) Azure DevOps service endpoint to connect to projects' pipelines.

- Add current stage name tag (release pipeline only)
- Add current release name tag (release pipeline only)
- Add user-defined tags
- Remove duplicated tags

## Prerequisites

For the task to work your release pipeline need to have a service endpoint with specific access to target project' pipelines to be able to update build tags.

There are two types of Azure DevOps **service endoints** supported:

Type | Name | Account
---- | ---- | -------
integrated | SystemVssConnection | Project Collection Build Service
specific | User specified | User specified

You may need to check and update build pipelines security section of Azure DevOps project allow the following access to user account of the service endpoint:

- View builds
- View build definition
- Update build information

Please refer to Azure DevOps [permissions and security roles documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/policies/permissions) for more details.

## How To Use

1. Add **Artifacts Tagger** task to your release pipeline
2. Select `Integrated Endpoint` or `Service Endpoint` endpoint type
3. Select default or specify custom tags to add to master build artifact

> You may need to create a new Azure Pipelines [service connection](https://docs.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints) using [PAT](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) token.

## Support

For aditional information and support please refer to [project repository](https://github.com/dmitryserbin/azdev-artifacts-tagger). To enable debug mode to help troubleshooting issues, please configure `DEBUG=artifacts-tagger:*` custom release [variable](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/variables).

For help with Azure DevOps and release pipelines please refer to [official documentation](https://docs.microsoft.com/en-us/azure/devops).
