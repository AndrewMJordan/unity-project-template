# Unity Project Template

Template repository for custom Unity project development.

## Overview

## Quick Start

### Azure DevOps
1. Create a new pipeline in Azure Pipelines.
2. Create a pipeline variable named `Custom.ProjectRoot`.
	- The value should be the relative path to your package. (Ex. `Project`)
3. Create a pipeline variable named `Custom.AccessToken.Dropbox`.
	- This is your access token for your Dropbox application (see [Dropbox OAuth Guide](https://www.dropbox.com/lp/developers/reference/oauth-guide))