The first part is the CI section of the tutorial. Due to the topic if you wish to follow along then this would need to be done outside of Katacoda. The explanation provided here should be enough to understand what is happening so that you can safely read along instead.

First we need to get the sample repository with all of the example setups.
`git clone https://github.com/bubriks/simple-web`{{execute T1}}

Then lets move in and see what we have.
`cd simple-web`{{execute T1}}
`ls`{{execute T1}}

What we are going to focus on is `.travis.yml` and `package.json`.
For `.travis.yml` it is a file that Travis CI will follow to show whether this version works or not.  

We can use this command to look at the `.travis.yml` file.  
`cat .travis.yml`{{execute T1}}

Inside we find:
```
language: node_js
node_js:
  - node
```
`language: node_js` specifies which language Travis expects and in this case it is JavaScript within the Node JS framework. `node_js: - node` tells Travis to use the newest stable release of Node JS. Notice that the file is missing any commands, this is because Travis has default behaviours. 

For Node JS Travis would run `npm install` or `npm ci`. Travis would run `npm ci` if it detects a `package-lock.json` which tells npm what dependencies the project is using. 

Travis would then also choose to run either `make test` or `npm test`. `npm test` is chosen if `package.json` exist. 

Essentially what Travis is doing is learn what language the project is using, get the appropriate dependencies, and run the test.
