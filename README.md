# Hive

Hive is a user-friendly Bitcoin wallet app for OSX.


## Requirements

* OSX 10.7 (Lion) or newer
* Java runtime (for now - required by bitcoinj lib)


## Building

First, clone the GitHub repository:

    git clone git@github.com:grabhive/hive-osx.git

Make sure you have CocoaPods installed:

    gem install cocoapods

Install the required pods:

    pod install

Now, import some Hive libraries which are kept in separate repositories as submodules:

    git submodule update --init --recursive

Before you build the project, you also need to install some additional libraries using homebrew:

    brew install libevent openssl maven
    brew link openssl --force

Then you can open the project workspace in Xcode (`Hive.xcworkspace`, not `Hive.xcodeproj`), hit the Run button and wait for it to build. Enjoy!


## Test vs. production network

Hive is currently set up to use the main blockchain. If you prefer to use the testing network to avoid risking real Bitcoin while testing the app, uncomment the line `#define TESTING_NETWORK 1` in `Hive-Prefix.pch` and rebuild the app.

**Warning: if you use the production network, be careful and don't transfer large amounts of bitcoins to the Hive wallet. The app is still in a beta phase and there's always a risk that something will go wrong and the wallet will be lost.**


## Contributing

Patches and pull requests are very welcome. If you want to send us any code, read the [Coding guidelines](https://github.com/grabhive/hive-osx/wiki/Code-style-guidelines) first.
