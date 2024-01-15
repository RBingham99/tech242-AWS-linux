## Webhooks
A webhook is when 1 service notifys another of a change.

# Setting up a webhook from github to jenkins
1) On the configre screen of your jenkins job set the "Branch Specifier" to "*/dev", then scroll down to "Build triggers" and tick "GitHub hook trigger for GITScm polling"
2) Go to your github repo, click on settings, and then webhooks
3) Click on add webhook
4) In the payload URL enter the jenkins server ID and port number followed by /github-webhook/, so it will look something like this `http://52.31.15.176:8080/github-webhook/`
5) You can leave all the other settings and just click add webhook
6) Now when your dev branch changes that job will trigger 