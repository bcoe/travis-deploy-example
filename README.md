# Travis Deploy Example

Example of using Travis CI to automatically publish your packages to npm, using:

* Travis CI's [npm deploy](https://docs.travis-ci.com/user/deployment/npm/) functionality.
* the [makeshift](https://github.com/nexdrew/makeshift) package, for generating an `.npmrc`
  file with your credentials in it.
* and the [standard-version](https://github.com/conventional-changelog/standard-version) package,
  for automating [semver](http://semver.org/) bumps and CHANGELOG generation.

## Setting `NPM_TOKEN` environment variable

To be able to install private packages and to publish on your behalf, Travis CI
needs your npm deploy token. After logging into npm, [this token can be found
in your `.npmrc` file](https://npme.npmjs.com/docs/workflow/travis.html#option-1-fetch-your-npm-enterprise-secret-token).

Once you fetch your token, set this as an environment variable in Travis CI called `NPM_TOKEN`:

![setting NPM_TOKEN](./screen-1.png)

## Installing Private npm Packages

`.npmrc` is npm's configuration file, amongst other things: it contains your auth information, and tells the npm
CLI what registry to install from. The following lines in our `.travis.yml` generate
a `.npmrc` [mapping the @bcoe scope](http://localhost:4000/cli/configuration.html#option-2-using-enterprise-for-private-packages-only) to the `registry.npmjs.org` registry:

```yaml
before_install:
  - npm i -g makeshift && makeshift -s @bcoe -r registry.npmjs.org
```

This allows us to install the private `@bcoe/super-secret-dependency` dependency.
