`.travis.yml` instructs Travis CI about what steps to follow.  

We can look inside by executing the following command. 
`cat .travis.yml`{{execute T1}}

Within the file we will find:
```
language: node_js
node_js:
  - node
```

`language: node_js` specifies which language Travis expects and in this case, it is JavaScript within the Node JS framework. 
`node_js: - node` tells Travis to use the newest stable release of Node JS.

Notice that the file is missing any commands, this is because Travis has default behaviors. 

For example, if Travis detects a `package-lock.json` file that holds dependencies for the project, it will use `npm ci` instead of `npm install`.
Same happening for tests, with it choosing to run `npm test` if `package.json` exists. In the case of this package missing, `make test` is run.

Essentially Travis is deciding on appropriate dependencies and running the test based on the language used by the project.