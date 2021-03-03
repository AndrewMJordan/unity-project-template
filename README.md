# Unity Project Template

Template repository for custom Unity project development.

## Overview
-	The default project location is `Project`
-	The [Build Utility](https://github.com/AndrewMJordan/build-utility) package is installed
-	Azure Pipelines build/deploy pipeline (self-hosted agent(s) required)

## Quick Start
1. Click "Use this template" (above).
2. Follow the generate repository screen.
	- OPTIONAL: check "Include all branches" to include the recommended branching workflow.
3. Clone the project to your workstation.
4. Edit the file `README.md` with your project's details.
5. Rename the project folder to your project's name.

## CI/CD with GitLab CI/CD
### Prerequisites
- Self-hosted runner
	- Make sure the runner is tagged with "unity"

## CI/CD with Azure DevOps
### Prerequisites
- Self-hosted Azure agent pool with Unity capabilities
- itch.io API key

### Setup
1. Create a new Azure Pipelines pipeline.

2. Edit YAML settings.
	1. Change Pipeline Name.
	2. Change "Default agent pool" to your Unity agent pool.
	3. Get sources
		- Set "Default branch for manual and scheduled builds" to `develop`.
		- Set "Clean" to `false`.
		- Set "LFS" to `true`.
		- Set "Shallow fetch" to `enabled` and "Depth" to `1`.3. 

3. Edit pipeline variables.

| Name | Value | Secret | Notes |
| --- | --- | --- | --- |
| `API.Butler` | `<YOUR_BUTLER_API_KEY>` | Yes |  |
| `Custom.Itch.Suffix` | `<ITCH_SUFFIX>` | No |  |
| `Custom.Itch.Game` | `<ITCH_GAME>` |  | No |
| `Custom.Itch.User` | `<ITCH_USERNAME>` | No |  |
| `Custom.ProjectRoot` | `<PATH_TO_PROJECT>` | No | The value should be the relative path to your package. (Ex. `Project`) |

4. Edit pipeline triggers.
	1. (Optional) Schedule `develop` for 00:00 UTC every day.

5. Upload a Unity license file.
	1. **Pipelines > Library > Secure Files > Add Secure File**
	2. Upload a Unity license file.
    	- Ex. Unity_v2017.x.ulf
	3. Edit the secure file.
	4. Set "Authorize for use in all pipelines" to `true`. 
