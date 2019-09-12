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
1. Put the Build ID in the header ([how to find the build id](/Find-the-build-id))
1. Put an Azure PAT with build permissions in the header ([create PAT](/Personal-Access-Token-\(PAT\)))

![image.png](/.attachments/service hooks settings.png)
