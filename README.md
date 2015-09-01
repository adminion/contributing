
# Adminion Contribution Guide

All are encouraged to contribute by way of submitting new Issues and Pull-Requests to help improve the quality of projects in the Adminion org.  Please see individual sections below regarding different types of contributions. 

# Release Strategy

All development, including semver-majorb changes, should be done in the master branch.  Master therefore has an unstable API and is used for incubation of breaking changes and new features. 

Immediately following a semver-major (i.e. v2.0.0) release,  a stable release branch for that major version (i.e. v2.x) should be cut from master. Semver-major and semver-patch commits from master should be cherry-picked into stable release branches where appropriate. Minor and patch releases should be made from their respective stable branches. (i.e. v2.x -> v2.0.1)


## Bugs
If you believe you have found a bug, please create an issue describing the bug, code that reproduces it, and the version of the project you are using.  If possible, please provide a pull request to fix or suggest how the bug may be resolved.  

Please follow the [Pull Request Guidelines](#pull-request-guidelines).

## New Features
Please follow the [Pull Request Guidelines](#pull-request-guidelines).

## Breaking Changes
Breaking *semver-major* changes will only be considered if they dramatically improve stability, performance, and/or usability with minimal code modifications for end-users.  Please follow the [Pull Request Guidelines](#pull-request-guidelines).

## Pull Request Guidelines

1. Fork the project repo
2. Create a new branch from `master`.  
3. Implement your feature/bugfix in that branch and please provide [jsdoc](http://usejsdoc.org/) compatible API documentation for new features (don't forget to credit yourself with the @author tag!).
4. Write/improve tests for your new feature/bugfix.
5. Verify your feature/bugfix passes all of *your* tests as well as all *existing* tests.
6. *Rebase* your branch on top of `adminion:master` to include others' changes.
7. Again, verify your feature/bugfix *still* passes *all* tests after rebasing.
8. Regenerate API Documentation and run a Coverage Report: `npm run docs && npm run coverage`.
9. Commit and push your branch to your repo.
10. Make a pull request from your branch into `adminion:master`.


If myself or others incorporate bugfixes/minor changes before reviewing your PR, you may be asked to rebase *again* prior to merging your PR.  

## Testing and Coverage

Tests are implemented using [Mocha](http://mochajs.org/) and a test coverage reports are generated by [Istanbul](https://gotwarlost.github.io/istanbul/).

Run the tests with:

    $ npm test

and generate a coverage report using:

    npm run coverage

Test files are located in `tests/` and the coverage reports will be generated in `coverage/`.

# Quality Control

Tests help us find and prevent bugs.  They should be thorough, but not redundant.  **Please** always include tests with your new features and ensure you patches pass existing tests.  *PRs with failing tests will not be merged; furthermore, PRs that decrease a project's test coverage will likely not be merged.  See [Testing and Coverage](#testing-and-coverage).*
