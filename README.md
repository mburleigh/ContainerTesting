_calibri/20_ 

Deploy the Azure Functions:

Create branch policy to require QA to sign off to merge branch: 

1. Click on project settings (gear icon in lower left)
2. Under 'Repos' select 'Policies' (**note:** make sure you are in the correct repository & branch)
3. Click the 'Add status policy' button
4. Add the policy that will get set when the QA tester approves the feature

![image.png](/.attachments/image-95ba4ba4-3079-4cf3-8762-02219547973a.png)

Add a web hook that will get called when a PR is changed:

1. Click on project settings (gear icon in lower left)
2. Click on 'Service Hooks'
3. Click the 'Create subscription' button
4. Scroll down to 'Web Hooks'
5. Click 'Next'

![image.png](/.attachments/image-6593a95b-d2c4-4f36-a5c0-1a152b826077.png)

Set up the web hook Trigger:

1. Choose the event type
1. Choose the repository
1. Choose the target branch
1. Optionally set the Change type, Requester group, and/or Reviewer

![image.png](/.attachments/image-7c30fc88-b017-415f-b88e-893d9a76a555.png)

Set up the web hook Action:

1. Enter the URL of the Pull Request Changed function (including the function key)
1. Put the Build ID in the header (instructions below)
1. Put an Azure PAT with build permissions in the header (instructions below)

![image.png](/.attachments/image-8fc5ae08-944b-49b6-8ac6-25a8db9cf93e.png)

How to find the build ID:

1. Open the build pipeline editor
1. Click on the variables tab
1. The build ID is the system.definitionid

![image.png](/.attachments/image-134eec83-1162-4c0b-86be-08fd3758450a.png)

How to set up a personal access token (PAT):

1. 