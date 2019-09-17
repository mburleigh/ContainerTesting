# Container Based Testing

## Assumptions:
* An existing code repository that will be tested in a container

## Setup
* Deploy [Azure Functions](https://github.com/mburleigh/Function.ContainerCleanup) that orchestrate the testing workflow
  * PullRequestChanged
  * Confirm
  * CleanupAndCompletePR
  * auth file
* Add a dockerfile to existing repository
* Create container registry (in Azure portal)
  * enable admin user
  * use admin user & password to generate auth (base64 encode username:password)
* Create container build pipeline
  * Required variables:
    * aciResourceGroup (resource group of ACI in Azure)
    * acrAuth (auth token for ACR [see above])
    * acrRegistry (name of Azure Container Registry [see above])
    * acrRepository (repository where container images are stored in the container registry)
      * does not have to be created in Azure first
    * cleanupCallbackUrl (url to the CleanupAndCompletePR function)
    * cleanupUrl (url to the Confirm function)
    * [PAT](https://github.com/mburleigh/ContainerTesting/blob/master/Personal-Access-Token-(PAT).md) (used to access AzDO; needs Code & Work Item scopes)
    * slackWebhook (Slack webhook url to send notification to)
  * Push image to ACR
    * ACR auth token
  * Create instance in ACI
* [Set up policy on target branch](https://github.com/mburleigh/ContainerTesting/blob/master/Create-Branch-Policy.md)
* [Create Webhook for pull request event](https://github.com/mburleigh/ContainerTesting/blob/master/Add-Web-Hook.md) (created/changed)
  * Link to PullRequestChanged function
  * Add headers:
    * [BuildId](https://github.com/mburleigh/ContainerTesting/blob/master/Find-the-build-id.md) (System.DefinitionId of container build pipeline)
    * PAT (requires build scope)
    * BuildAgent (must match Agent Specification of container build pipeline)
  
 
 
## This talk (in various versions) has been presented at:
* Philly CodeCamp 2019.1
* CodePaLOUsa 2019
* BaltoMSDN September 2019


