# TwitterKit-Rx


`TwitterKit-Rx` allows you to use the beautiful `rx` syntax to access the Twitter API. After logging in your user in one of the provided ways by the [Fabric SDK](https://docs.fabric.io/ios/twitter/authentication.html), create a `TWTRAPIClient` object by providing the `userID`. You can then call a method in this way:

```swift
let client = TWTRAPIClient(userID: userID)
let disposeBag = DisposeBag()

// Loads a Twitter User
Twitter.sharedInstance()
	.rx_loadUserWithID(userID, client: self.session.client!)
	.subscribe(onNext: { user in
       	// Use the TWTRObject
      	}, onError: { error in
          print("Failed in requesting user data with error: \(error)!")
		}, onCompleted: nil, onDisposed: nil)
	.addDisposableTo(self.disposebag)
```


## Installation

TwitterKit-Rx is **not** available through [CocoaPods](https://github.com/CocoaPods/) at the moment. I'm having issues in specifying a dependecy on the Fabric SDK when creating my Podspec. Any help or PRs is welcome on [this issue](https://github.com/CocoaPods/CocoaPods/issues/4745). 👍

Do it the old way, drag in your project the `TwitterKit-Rx.swift` class.

## Requirements
The project requires iOS 8.0.

## Author

I'm Patrick Balestra, tweet me [@BalestraPatrick](http://www.twitter.com/BalestraPatrick) or email me [me@patrickbalestra.com](mailto:me@patrickbalestra.com).

## License

TwitterKit-Rx is available under the MIT license. See the LICENSE file for more info.
