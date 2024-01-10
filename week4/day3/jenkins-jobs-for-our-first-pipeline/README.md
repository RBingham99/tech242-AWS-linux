# Jenkins jobs for our first pipeline
## Job 1
Job one will run the tests on our jsonvh app.
To set it up:
1) Click "new item"
2) Enter the name of your job and click on "freestyle project".<br>
   ![Jenkins name job](../../../readme-images/jenkins-name-job.png)
3) Give the job a description
4) Tick "discard old builds", and enter a number in the "max # of builds to keep" option.<br>
   ![Jenkins discard old builds](../../../readme-images/jenkins-discard-old-builds.png)
5) Click "github project" and enter the repositories HTTPS URL
6) Scroll down to "Source code management" and select "Git"
7) Under "Repository URL" paste in the repositories SSH URL<br>
   ![Jenkins source code management](../../../readme-images/jenkins-source-code-management.png)
8) Then click the add button and Jenkins and set up the credentials by:
   1) Changing the "kind" to "SSH Username with private key" 
   2) Enter the name of your SSH key into both the "ID" and "Username" boxes
   3) Enter a description in the "description" box<br>
   ![Jenkins ssh credentials](../../../readme-images/jenkins-ssh-credentials.png)
   4) Click "Enter directly" under "Private key"
   5) Click the blue "add" button
   6) Then go to your terminal and navigate to the folder your key is stored in
   7) Use the command `cat name-of-your-key` without the .pub at the end, as we need the private key
   8) Copy the output of the command, from the first - to the last -
   9) Paste that into the "Key" box and click "add"<br>
   ![Jenkins ssh private key](../../../readme-images/jenkins-ssh-private-key.png)
9)  In the "Branches to build" section, change "Branch Specifier" to "*/dev"
10) Scroll down to "Build steps", click on "Add build step" and select "Invoke top-level Maven targets"<br>
    ![Jenkins build steps](../../../readme-images/jenkins-build-steps.png)
11) Select the maven version you are using
12) In goals type the maven command you want to use, I used "package test"<br>
    ![Jenkins build steps](../../../readme-images/jenkins-build-steps.png)
13) Now click save and you can run your job to see if it works

# Job 2
1) Click "new item"
2) Enter the name of your job and click on "freestyle project".<br>
   ![Jenkins name job](../../../readme-images/jenkins-name-job.png)
3) Give the job a description
4) Tick "discard old builds", and enter a number in the "max # of builds to keep" option.<br>
   ![Jenkins discard old builds](../../../readme-images/jenkins-discard-old-builds.png)
5) Click "github project" and enter the repositories HTTPS URL
6) Scroll down to "Source code management" and select "Git"
7) Under "Repository URL" paste in the repositories SSH URL<br>
   ![Jenkins source code management](../../../readme-images/jenkins-source-code-management.png)
8) Select the credentials we made earlier
9) In the "Branches to build" section, change "Branch Specifier" to "*/dev"
10) Click "Add additional behaviours" and select "Merge before build"
11) Enter "origin" as "Name of repository"
12) Enter "main" as "Branch to merge to"<br>
    ![Jenkins additional behaviours](../../../readme-images/jenkins-additional-behaviours.png)
13) Scroll down, click on "Add post-build action" and select "Git publisher"
14) Tick "Push Only If Build Succeeds" and "Merge Results"<br>
    ![Jenkins git publisher](../../../readme-images/jenkins-git-publisher.png)
15) Click save
16) Navigate to the configure section for job 1
17) Scroll to the bottom, click "Add post-build action" and select "Build other projects"
18) Choose job 2 and set to "Trigger only if build is stable"