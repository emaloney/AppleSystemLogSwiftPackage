# A Swift package for ASL

This project contains a Swift Package Manager (SPM) declaration allowing the C headers of the Apple System Log (ASL) to be imported from Swift.

**Note:** This Swift package will function only on Apple platforms.

## Other Projects

If you're interested in using the ASL from Swift, there are a couple of options that provide a higher-level API:

- [CleanroomASL](https://github.com/emaloney/CleanroomASL) — An API providing direct access to the Apple System Log via a *more Swifty* programming model
- [CleanroomLogger](https://github.com/emaloney/CleanroomLogger) — A high-level Swift logging API that—on Apple platforms—uses [CleanroomASL](https://github.com/emaloney/CleanroomASL) under the hood

## Specifying ASL as a dependency

Using the Swift Package Manager, you can import and use the C-based ASL API from Swift.

To do this, you need to add the appropriate declaration to the `dependencies` section of your project's `Package.swift` manifest.

If you're starting a project *NewApp* from scratch and you wish to use ASL, you could do this by creating a new `Package.swift` file that looks like:

```swift
import PackageDescription

let package = Package(
        name: "NewApp",
        dependencies: [
            .Package(url: "https://github.com/emaloney/AppleSystemLogSwiftPackage", majorVersion: 1)
        ]
    )
```

Then, when you build with SPM, you will be able to use the ASL API from Swift by adding the following import as appropriate to your Swift files:

```swift
import ASL
```
