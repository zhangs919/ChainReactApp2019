# The official Chain React App for #ChainReact2019

- React Native app utilizing [Ignite CLI](https://github.com/infinitered/ignite) and the [Ignite Bowser](https://github.com/infinitered/ignite-bowser) boilerplate

## :arrow_up: How to Setup

**Step 1:** git clone this repo:

**Step 2:** cd to the cloned repo:

**Step 3:** Run the setup script: `./bin/setup`

## :arrow_forward: How to Run App

1.  cd to the repo
2.  Run Build for either OS

- for iOS
  - run `react-native run-ios`
- for Android
  - run `react-native run-android`

# SecretsssSSSsssSSsssSSSsss :snake:

If you are working on the AWS AppSync talk discussion feature of the app, you will need a `.env` file with the proper API token, as well as the `amplify-meta.json` file. Please ping `@jamon` in the #chainreact channel of the [Infinite Red community Slack](http://community.infinite.red) and we'll hook you up!

# Deploying

1. Follow steps 2-5 in the secrets repo (See Jamon or Robin for access)
2. Open the Xcode Workspace and go to Build Settings. Make sure "Manage certificates automatically" is not checked, and select the correct certificate. If you don't see any certificates you may need to run `fastlane match development` and `fastlane match appstore`
3. To deploy iOS beta:

```
cd ios
bundle
bundle exec fastlane ios bump_build_number
bundle exec fastlane ios beta
```

- If prompted for an app-specific password, it's located in the secrets repo.
- If the build is successful, commit the new build number.

4. To deploy Android beta:

```
cd android
bundle
bundle exec fastlane android beta
```

- If the build was successful, commit the build number

# :no_entry_sign: TSLint Compliant

This project adheres to TSLint and Prettier. We suggest you enable linting to keep your project compliant during development. You can lint the project by running `yarn lint`.

**To Lint on Commit**

This is implemented using [husky](https://github.com/typicode/husky). There is no additional setup needed.

**Bypass Lint**

If you have to bypass lint for a special commit that you will come back and clean (pushing something to a branch etc.) then you can bypass git hooks with adding `--no-verify` to your commit command.

**Understanding Linting Errors**

The linting rules are from tslint-config-prettier. [Regular TS errors can be found with descriptions here](https://palantir.github.io/tslint/rules/).

# Detox End-To-End Testing

## Setup

_Note that Detox is only configured for macOS._

To get your Detox tests up and running, you'll need to install some global dependencies:

1. Install the latest version of [Homebrew](https://brew.sh/)

2. Make sure you have Node installed (at least 8.6.0).

3. Install `applesimutils`, which will allow Detox to communicate with the iOS simulator:

```bash
brew tap wix/brew && brew install applesimutils
```

4. Install the Detox CLI

```bash
  yarn global add detox-cli
```

## Adding tests

We've gotten you started with `./e2e/firstTest.spec.js`, which tests that the two main example screens render properly.

Note that in order to pick up elements by ID, we've added the `testID` prop to the component.

## Running tests

1. Start the packager

```
yarn start
```

2. Run the app

In a separate terminal window from the packager:

```
yarn build:e2e
```

3. Run the tests

```
yarn test:e2e
```

For more information, make sure to check out the official [Detox Docs](https://github.com/wix/Detox/blob/master/docs/README.md)
