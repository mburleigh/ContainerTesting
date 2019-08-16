# Introduction 
TODO: Give a short introduction of your project. Let this section explain the objectives or the motivation behind this project.

calibri/20 

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

![image.png](/.attachments/image-96b6dc69-db52-474e-af5f-32eff81e270d.png)

![image.png](/.attachments/image-8fc5ae08-944b-49b6-8ac6-25a8db9cf93e.png)