# Travis Deploy Example

Example of using Travis CI to automatically publish your packages to npm, using:

* Travis CI's [npm deploy](https://docs.travis-ci.com/user/deployment/npm/) functionality.
* the [makeshift](https://github.com/nexdrew/makeshift) package, for generating an `.npmrc`
  file with your credentials in it.
* and the [standard-version](https://github.com/conventional-changelog/standard-version) package,
  for automating [semver](http://semver.org/) bumps and CHANGELOG generation.

### Setting `NPM_TOKEN` environment variable

To be able to install private packages and to publish on your behalf, Travis CI
needs your npm deploy token. After logging into npm, [this token can be found
in your `~/.npmrc` file](https://npme.npmjs.com/docs/workflow/travis.html#option-1-fetch-your-npm-enterprise-secret-token).

Once you fetch your token, set this as an environment variable in Travis CI called `NPM_TOKEN`:

![setting NPM_TOKEN](./screen-1.png)
