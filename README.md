# CI/CD Pipeline
## Requirements
- [x] Create jenkins job called 'firstname-lastname-deploy'. [Click here](https://github.com/ugneokmanaite/NodeJS_AWS_Deploy_code) for steps in setting this up 
- [x] Set this job to run when the CI testing job has finished successfully
- [x] Make a change to the homepage of the app and push your code to the develop branch to test your pipeline 
- [x] The job should pull from master only and not push
- [x] Use rsync and ssh to upload files to a remote server