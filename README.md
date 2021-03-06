# Facebook Image Picker

[![Version](https://img.shields.io/cocoapods/v/MBFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/MBFacebookImagePicker)
[![Platform](https://img.shields.io/cocoapods/p/MBFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/MBFacebookImagePicker)
[![License](https://img.shields.io/cocoapods/l/MBFacebookImagePicker.svg?style=flat)](http://cocoapods.org/pods/MBFacebookImagePicker)

A simple image picker for Facebook images written in Swift.

## Requirements

* Xcode 8
* iOS 8.0+ target deployment
* FBSDKCoreKit, FBSDKLoginKit (>= 4.0)
* Swift 3 project 

## Installation

### CocoaPods

Add the following line to your Podfile:

```ruby
pod "MBFacebookImagePicker"
```

#### With example project:

Enter the following line in your terminal:

```ruby
pod try MBFacebookImagePicker
```

### Manually
Download the project or clone the repo. Import the `MBImagePicker` folder into your project. Make sure you have the `FBSDKCoreKit`, `FBSDKCoreKit`, and `Bolts` frameworks imported. 

### Running the example project
If you downloaded or cloned the project, you must first run `pod install` from the Example directory to install all dependencies. 

Also make sure to replace `FacebookAppID` under `URL types` and `FacebookAppID` in `info.plist`.

## Usage

Make sure that your application has been setup with the [Facebook SDK](https://developers.facebook.com/docs/ios/getting-started).

Import the library : 

```swift
import MBFacebookImagePicker
```

Show the picker:

```swift
let imagePicker = MBFacebookImagePickerController()
imagePicker.finishedCompletion = { [weak self] (result) in
    self?.dismiss(animated: true, completion: nil)
    switch result {
        case .completed(let image): self?.imageView.image = image
        case .failed(let error): print("failed with error: \(error)")
        case .cancelled: print("Cancelled!")
    }
}
present(imagePicker, animated: true, completion: nil)
```


## Translations 

MBImagePicker uses the following translation keys:

```
"MBIMAGEPICKER_NO_ALBUMS_FOUND"     = "No albums found";
"MBIMAGEPICKER_ALBUMS"              = "Albums";

"MBIMAGEPICKER_ERROR_ALERT_TITLE"   = "Ooops...";
"MBIMAGEPICKER_NETWORK_ERROR"       = "Network unavailable, please try again";
"MBIMAGEPICKER_UNKNOWN_ERROR"       = "Something went wrong, please try again";

"MBIMAGEPICKER_NO_PICTURES_FOUND"   = "Could not find any pictures\nin your photo album";

"MBIMAGEPICKER_CANCEL"              = "Cancel";
"MBIMAGEPICKER_OK"                  = "OK";
```
Add the keys to your `localizable.strings` and modify the strings for you respective language(s).

## License

MBFacebookImagePicker is available under the MIT license. See the LICENSE file for more info.