# CI/CD Pipeline :cloud:
## Requirements
- [x] Create jenkins job called 'firstname-lastname-deploy'. [Click here](https://github.com/ugneokmanaite/NodeJS_AWS_Deploy_code) for steps in setting this up 
- [x] Set this job to run when the CI testing job has finished successfully
- [x] Make a change to the homepage of the app and push your code to the develop branch to test your pipeline 
- [x] The job should pull from master only and not push
- [x] Use rsync and ssh to upload files to a remote server

# Step-by Step

## Part 1- CI

1. *Download code* & store it in a folder which stores all of your code to keep it organised 

2. `git remote --v` provides location of the file online

We want to remove this remote link as it's not our repository location

`git remote rm origin` and then check using `git remote --v` to ensure it has been removed

3. *Create a new repository* & follow instuctions provided on Github

4. Explore the app ! Ensure you know what files & folders it includes e.g. 

using `subl .` to make this process more visual

5. Now let's set up Jenkins! [Click here](https://github.com/ugneokmanaite/NodeJS_AWS_Deploy_code) for steps in setting this up 


## Part 1- CD