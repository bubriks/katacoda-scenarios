Now we move onto the `package.json` file. This file is created when you run `npm init` and it tells npm what your project is about. 

We can use this command to look at the `package.json` file.  
`cat package.json`{{execute T1}}

If you look at the file you will notice this section:
```
...
"scripts": {
    "test": "mocha"
  }
...
```

This project is using the Mocha JavaScript test framework and the section above is telling npm to run Mocha.  

In this project there is a `test.js` which Mocha looks for when it is called. If later you want to have multiple test files, Mocha can instead look for a test folder and you can store them like this:

```
test/
├── test_1.js
└── test_2.js
```

When Travis is done running the test, they will show the outcome of the test. This is done by showing it in their own dashboard and through GitHub Actions.

We can now exit the folder.
`cd ..`{{execute T1}}