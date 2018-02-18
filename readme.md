# LaunchAtLogin

Note: Forked from [sindresorhus/LaunchAtLogin](https://github.com/sindresorhus/LaunchAtLogin).

> Add "Launch at Login" functionality to your sandboxed macOS app in seconds

## Requirements

- macOS 10.10+
- Xcode 9+
- Swift 4+


## Install with [Carthage](https://github.com/Carthage/Carthage#getting-started)

```
github "sindresorhus/LaunchAtLogin"
```

Add a new ["Run Script Phase"](http://stackoverflow.com/a/39633955/64949) below "Embed Frameworks" in "Build Phases" with the following:

```sh
./Carthage/Build/Mac/LaunchAtLogin.framework/Resources/copy-helper.sh
```

## Install with Cocoapods

```
pod "LaunchAtLogin", :git => "https://github.com/valeIT/LaunchAtLogin.git"
```

Add a new ["Run Script Phase"](http://stackoverflow.com/a/39633955/64949) below "Copy Pods Resources" in "Build Phases" with the following:

```sh
./Pod/LaunchAtLogin/LaunchAtLogin/copy-helper.sh
```

## Usage

Use it in your app:

```swift
import LaunchAtLogin

print(LaunchAtLogin.isEnabled)
//=> false

LaunchAtLogin.isEnabled = true

print(LaunchAtLogin.isEnabled)
//=> true
```

*Note that the [Mac App Store guidelines](https://developer.apple.com/app-store/review/guidelines/) requires "launch at login" functionality to be enabled in response to a user action. This is usually solved by making it a preference that is disabled by default.*


## How does it work?

The framework bundles the helper app needed to launch your app and copies it into your app at build time.


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
