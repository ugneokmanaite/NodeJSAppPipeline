# CI/CD Pipeline :cloud:
## Requirements
- [x] Create jenkins job called 'firstname-lastname-deploy'. [Click here](https://github.com/ugneokmanaite/NodeJS_AWS_Deploy_code) for steps in setting this up 
- [x] Set this job to run when the CI testing job has finished successfully
- [x] Make a change to the homepage of the app and push your code to the develop branch to test your pipeline 
- [x] The job should pull from master only and not push
- [x] Use rsync and ssh to upload files to a remote server

# Part 1- CI

## 1. *Download code*
Store it in a folder which stores all of your code to keep it organised 

## 2. `git remote --v` 
Provides location of the file online

We want to remove this remote link as it's not our repository location

`git remote rm origin` and then check using `git remote --v` to ensure it has been removed

## 3. *Create a new repository*
 And follow instuctions provided on Github

## 4. Explore the app ! 
Ensure you know what files & folders it includes e.g. 

using `subl .` to make this process more visual

## 5. Now let's set up Jenkins!
 [Click here](https://github.com/ugneokmanaite/NodeJS_AWS_Deploy_code) for steps in setting this up 

# Part 2- CD
- So now that the code test ran successfully, we will create a new job which will come from the first one 

- We want to use AWS as our remote server

## 1. Create a name for new item in Jenkis
` ugne-okmanaite-deploy-v2`

choose freestyle project

## 2. Use the same Github project link as previously 

## 3. No need to restrict where it can be build
We are not testing at this stage so it is no longer required

## 4. Source Code Management
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/source_code_management.JPG)

 '*/master' branch is being used to build

## 5. Build Triggers
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/build_triggers.JPG)

ensure that ` Build after other projects are build` is selected

## 6. Build Environment
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/build_environment.JPG)
 
 We need the key of the machine- in this instance its `DevOpsStudents.pem`

## 7. scp & nsync
- We don't need to test the code just to push so we need to sync the required files

`copy the app`

`copy the evironment setup (e.g. config, sh files)`

`then we need to run these!!!`

We need to select execute shell and enter the following
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/execute_shell.jpg)

## 8.  Go into the app & make some changes to the homepage via index.ejs
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/homepage_changes.png)

## 9. Opening port 22 for Jenkins
- Go on AWS E2 Dashboard 
- In the instance, under security group select inbound rules
- add rule
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/inbound_rule.jpg)
- Save

Now this should appear 
![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/ports.jpg)

- port 22 is now open via personal IP & Jenkins IP

## 10. Checkout with changes 
- in bash terminal enter `git checkout -b develop`
- followed by add, commit & push 
- this will commit new changes to the branch 
- changes will not be pushed to master

![image](https://github.com/ugneokmanaite/NodeJSAppPipeline/blob/master/images/ugne_was_here.jpg)



