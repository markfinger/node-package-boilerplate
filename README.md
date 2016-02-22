node-package-boilerplate
========================

Create an empty repo
--------------------

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
rm README.md
echo "#" $REPO_NAME >> README.md
```

Commit to the new repo
----------------------

```
git init
git add -A
git commit -m 'Initial commit.'
git remote add origin git@github.com:markfinger/$REPO_NAME.git
git push -u
```


Init
----

```
npm init
```


Dependencies
------------

```
npm install --save-dev \
  `# npm run build` \
  babel-cli babel-preset-es2015 yargs \
  `# npm test` \
  mocha chai source-map-support \
  `# npm run lint` \
  eslint babel-eslint
```


Integrations
------------

Go to https://travis-ci.org/profile/markfinger and toggle the repo on.


Should probably...
------------------

Inspect [.travis.yml](.travis.yml) and update the node version that
we target to latest.

[.babelrc](.babelrc) should be configured to only apply the transforms
necessary for the specific version of node. If can omit some, push the
changes upstream to
[this repo](https://github.com/markfinger/node-package-boilerplate).