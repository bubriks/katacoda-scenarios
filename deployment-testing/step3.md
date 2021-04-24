Now with Travis CI explored, the focus in this step will be on setting up a GitHub repository with Travis CI. For this, you will need GitHub and Travis CI account.  

First, we must start by creating a GitHub repository.  
[new repository](https://github.com/new)  

For example:  
* repository name: `travis-test`  
* `public` repository  

Once the repository is created we should jump to Travis CI.  
[Travis CI](https://www.travis-ci.com/)

Sign in (if you have an account) or sign up (for first-time users) with your GitHub account.  

Once you are signed in you will be placed into the Travis dashboard.  

Go into settings by clicking on your profile and selecting settings.  

Click on the `activate` button if you haven't and choose which repository you want Travis to work on. For example this example you can just choose `travis-test`.

Now that Travis knows where to look, we can upload the simple web to the repository. 

Travis will start working after `.travis.yml` if found. This means that for the first push containing the `.travis.yml` file, it will not run. After this, all changes would cause Travis to be run.

Now that the CI/CD section is finished. You can combine what you have learned here with the upcoming A/B section to create a pipeline that will directly integrate and deploy A/B testing. You can set it up so that your newest change with be tested againts the currently deployed version. This is quite advanced and since this tutorial aims to cover the basics we will not go over this specific scenario.