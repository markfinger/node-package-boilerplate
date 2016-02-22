node-package-boilerplate
========================

Create a repo
-------------

https://github.com/new

```
export REPO_NAME=...
```


Clone the boilerplate
---------------------

```
git clone --depth=1 --branch=master git@github.com:markfinger/node-package-boilerplate.git $REPO_NAME
rm -rf $REPO_NAME/.git
cd $REPO_NAME
```


Init the project and dependencies
---------------------------------

```
npm init

# Build deps
npm install --save-dev babel-cli babel-preset-es2015 yargs

# Test deps
npm install --save-dev mocha chai source-map-support

# Lint deps
npm install --save-dev eslint babel-eslint
```


Setup
-----

Add the following to package.json

```js
{
  // ...
  "scripts": {
    "test": "mocha --require source-map-support/register --reporter spec 'lib/**/tests/*.js'",
    "_test": "mocha --reporter spec 'lib/**/tests/*.js'",
    "lint": "eslint runtime/*.js src/**",
    "build": "./scripts/build.js"
  }
}
```

Probably want to inspect [.travis.yml](.travis.yml) and update the node
version that we target to latest. Go to
https://travis-ci.org/profile/markfinger and toggle the repo.

[.babelrc](.babelrc) should be configured to only apply the transforms
necessary for the specific version of node. If can omit some, push the
changes upstream to
[this repo](https://github.com/markfinger/node-package-boilerplate).


Commit to repo
--------------

```
git init
git add -A
git commit -m 'Initial commit.'
git remote add origin git@github.com:markfinger/$REPO_NAME.git
git push -u
```
