Now with Travis CI explored, the focus in this step will be on setting up a GitHub repository using Travis CI.
The following steps require some work to be done outside of the Katacoda environment, therefore,
if you feel confident in your understanding of the topic feel free to simply read through.

First, we must start by creating a GitHub repository.  
[new repository](https://github.com/new)  

For example:  
* repository name: `travis-test`  
* `public` repository  

Once the repository is created we should jump to Travis CI.  
[Travis CI](https://www.travis-ci.com/)

Login with your GitHub account.  

Once you are signed in you will be placed into the Travis dashboard.  
From here go into settings by clicking on your profile and selecting settings.  
Click on the `activate` button if you haven't and choose which repository you want Travis to work on. For our example, you can just choose `travis-test`.

Now that Travis has access to your repository, you can upload `simple-web` contents to verify that it works. 

Notice, that Travis will start functioning only if `.travis.yml` is found in the directory.