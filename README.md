# Unity Project Template

Template repository for custom Unity project development.

## Overview
-	The default project location is `./Project`
-	The [Build Utility](https://github.com/AndrewMJordan/build-utility) package is installed

## Quick Start
1. Click "Use this template" (above).
2. Follow the generate repository screen.
	- OPTIONAL: check "Include all branches" to include the recommended branching workflow.
3. Clone the project to your workstation.
4. Edit the file `./README.md` with your project's details.
8. Rename the project folder to your project's name.

### Azure DevOps
1. Create a Variable Group named "Authentication".
2. Add a variable named "Authentication.Dropbox".
	- The value should be your Dropbox application access token. (see [Dropbox OAuth Guide](https://www.dropbox.com/lp/developers/reference/oauth-guide))
	- Change variable type to secret.
3. Create a new Azure Pipelines pipeline.
4. Add a variable named `Custom.ProjectRoot`.
	- The value should be the relative path to your package. (Ex. `Project`)
5. Change the "Default agent pool for YAML" to an agent pool with Unity capabilities.