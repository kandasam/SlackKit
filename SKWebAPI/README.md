# SKWebAPI

Make requests to the [Slack Web API](https://api.slack.com/web) in Swift.

## Installation

### CocoaPods

Add SKWebAPI to your `Podfile`:

```
use_frameworks!
pod 'SlackKit/SKWebAPI'
```

### Carthage

Add SlackKit to your `Cartfile`:

```
github "pvzig/SlackKit"
```
and run

```
carthage bootstrap
```

Drag the built `SKWebAPI.framework` and it's dependency `SKCore.framework` into your Xcode project.

### Swift Package Manager

Add SlackKit as a dependency to your `Package.swift` and specify `SKWebAPI` as a target dependency:

```swift
import PackageDescription
  
let package = Package(
    name: "SampleApp",
    products: [
        .executable(
            name: "SampleApp",
            targets: ["SampleApp"]),
    ],
    dependencies: [
        .package(url: "https://github.com/pvzig/SlackKit.git", .upToNextMinor(from: "4.2.0")),
    ],
    targets: [
        .target(
            name: "SampleApp",
            dependencies: ["SKWebAPI"])
    ]
)

```

## Usage
To use the library in your project import it:

#### Carthage & SPM

```swift
import SKWebAPI
```

#### CocoaPods

```swift
import SlackKit
```

### The Basics
Initialize an instance of `SKWebAPI` with a Slack auth token and make your requests:

```swift
let webAPI = WebAPI(token: xoxp-SLACK_AUTH_TOKEN)
webAPI.authenticationTest(success: { (user, team) in
	print("\(user) - \(team)")
}, failure: nil)
```

### Web API Methods
SlackKit currently supports the a subset of the Slack Web API that is available to bot users:

| Web APIs      |
| ------------- |
| `api.test`|
| `api.revoke`|
| `auth.test`|
| `channels.history`|
| `channels.info`|
| `channels.list`|
| `channels.mark`|
| `channels.create`|
| `channels.invite`|
| `channels.setPurpose`|
| `channels.setTopic`|
| `chat.delete`|
| `chat.meMessage`|
| `chat.postMessage`|
| `chat.update`|
| `emoji.list`|
| `files.comments.add`|
| `files.comments.edit`|
| `files.comments.delete`|
| `files.delete`|
| `files.info`|
| `files.upload`|
| `groups.close`|
| `groups.history`|
| `groups.info`|
| `groups.list`|
| `groups.mark`|
| `groups.open`|
| `groups.setPurpose`|
| `groups.setTopic`|
| `im.close`|
| `im.history`|
| `im.list`|
| `im.mark`|
| `im.open`|
| `mpim.close`|
| `mpim.history`|
| `mpim.list`|
| `mpim.mark`|
| `mpim.open`|
| `oauth.access`|
| `pins.add`|
| `pins.list`|
| `pins.remove`|
| `reactions.add`|
| `reactions.get`|
| `reactions.list`|
| `reactions.remove`|
| `rtm.start`|
| `stars.add`|
| `stars.remove`|
| `team.info`|
| `users.getPresence`|
| `users.info`|
| `users.list`|
| `users.setActive`|
| `users.setPresence`|