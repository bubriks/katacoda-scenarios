As for setting up a GitHub repository with Travis CI, you will need a GitHub account and a Travis CI account. We would then describe how to set it up with the simple web files.  

First we need to create a GitHub repository.  
[new repository](https://github.com/new)  

For example:  
* repository name: `travis-test`  
* `public` repository  

Once the repository is created we should jump to Travis CI.  
[Travis CI](https://www.travis-ci.com/)

Sign in or sign up with your GitHub account.  

Once you are signed in you will be placed into the dashboard.  

Then go to the settings by clicking on your profile and clicking on settings.  

Click on the `activate` button if you haven't and choose which repository that you want Travis to work on. For example you can just choose one repository and choose the `travis-test` one.

Now that Travis knows where to look, we can upload the simple web to the repository. Travis will react for every git push onto the GitHub repository after `.travis.yml` if found. This means that for the first first push containing the `.travis.yml` file, it will not run. After this exist on the remote repository though all pushes afterwards would be run by Travis.