# Travis Deploy Example

Example of using Travis CI to automatically publish your packages with private
dependencies to npm.

This demo uses:

* Travis CI's [npm deploy](https://docs.travis-ci.com/user/deployment/npm/) functionality.
* the [makeshift](https://github.com/nexdrew/makeshift) package, for generating a `.npmrc`
  file with your credentials in it.
* The [standard-version](https://github.com/conventional-changelog/standard-version) package,
  for automating [semver](http://semver.org/), and CHANGELOG generation.
