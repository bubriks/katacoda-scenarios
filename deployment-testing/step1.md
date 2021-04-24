As already mentioned we begin by looking at the basics of continuous integration. This implementation requires some work to be done outside the Katacoda environment, therefore, if you feel confident in your understanding of the topic feel free to simply read through.

First, we need to get the sample repository with all contents necessary for this tutorial (including A/B testing later on).
`git clone https://github.com/bubriks/simple-web`{{execute T1}}

With a successfully downloaded repository, we can move in and see what we have.
`cd simple-web`{{execute T1}}
`ls`{{execute T1}}

What we are going to focus on is `.travis.yml` and `package.json`.

`.travis.yml` instructs Travis CI about steps to follow.  

Let us look inside it.  
`cat .travis.yml`{{execute T1}}

Inside we will find:
```
language: node_js
node_js:
  - node
```

`language: node_js` specifies which language Travis expects and in this case, it is JavaScript within the Node JS framework. 
`node_js: - node` tells Travis to use the newest stable release of Node JS.

Notice that the file is missing commands, this is because Travis has default behaviors. 

For example, if Travis detects a `package-lock.json` file that holds dependencies for the project, it'll use `npm ci` otherwise `npm install`.
Same happening for tests, with it choosing to run `npm test` if `package.json` exists. In the case of this package missing, `make test` is run.

Essentially Travis is deciding on appropriate dependencies and running the test based on the language used by the project.
