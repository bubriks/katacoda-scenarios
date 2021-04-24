Now moving on to `package.json` file.

This file is created when you run `npm init` and it tells npm what your project is about. 

When looking inside the `package.json` file  
`cat package.json`{{execute T1}}   
you will notice this section:
```
...
"scripts": {
    "test": "mocha"
  }
...
```

This means that project is using the Mocha JavaScript test framework.  

In this project, there is a `test.js` that Mocha looks for when it is called. If there is a desire to have multiple test files, Mocha can instead look for a test folder and you can store them like this:

```
test/
├── test_1.js
└── test_2.js
```

When Travis is done running tests it will show their outcomes. This visible in the Travis CI dashboard.

We can now exit the folder.  
`cd ..`{{execute T1}}