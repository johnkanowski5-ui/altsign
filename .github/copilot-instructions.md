# Copilot Instructions

## Project

AltSign is an Objective-C and Objective-C++ iOS/macOS framework for Apple developer account management and app signing. The Xcode project is `AltSign.xcodeproj`; the CocoaPods specification is `AltSign.podspec`.

- `AltSign/Apple API/` contains Apple API and authentication code.
- `AltSign/Model/` contains framework models.
- `AltSign/Resources/` and `AltSign/Signing/` contain signing-related resources and implementation.
- `AltSign/ldid/` and `Dependencies/` contain ldid, CoreCrypto, OpenSSL, minizip, and plist dependencies.

## Changes

- Keep changes focused and preserve public API compatibility unless the task requires otherwise.
- Follow the conventions in the nearest related files. Public Objective-C declarations generally use `ALT` prefixes and nullability annotations.
- Check both the Xcode project and the podspec when adding or removing source files, resources, or public headers; source membership is not necessarily automatic.
- Avoid unrelated edits to vendored or third-party code.

## Build and verification

Run builds on macOS with Xcode installed:

```sh
xcodebuild -project AltSign.xcodeproj -scheme AltSign -destination 'generic/platform=iOS Simulator' build
xcodebuild -project AltSign.xcodeproj -scheme AltSign-macOS -destination 'generic/platform=macOS' build
```

The shared schemes currently declare no testables. Do not claim tests passed unless a relevant test target has been added and run. This workspace may be running on Linux, where `xcodebuild` and Apple SDKs are unavailable; report that limitation instead of substituting an unrelated build check.
