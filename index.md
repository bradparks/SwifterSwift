---
layout: default
---

A handy collection of native Swift 3 extensions to boost your productivity.

### [Whats New in v1.0.4?](./new)

## Requirements:

Xcode 8 (or later) with Swift 3.
This library is made for iOS 8 or later, however most of the extensions should work on watchOS, tvOS, and macOS



## Installation

### CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

To integrate SwifterSwift into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '8.0'
use_frameworks!

target '<Your Target Name>' do
    pod 'SwifterSwift' , :git => 'https://github.com/omaralbeik/SwifterSwift.git'
end
```

Then, run the following command:

```bash
$ pod install
```

### Manually

Add the [extensions](//github.com/omaralbeik/swiftierswift/tree/master/Extensions) folder to your Xcode project to use all extensions, or a specific extension.



## How to contribute:

SwifterSwift is in its early stages, any feedback is appreciated and welcomed.
Please refer to the [contributing guidelines](./contributing) before participating.


## [List Of Extensions](./extensionstable)

-  [Array extensions](./extensionstable#array-extensions)
-  [Character extensions](./extensionstable#character-extensions)
-  [Convenience extensions](./extensionstable#convenience-extensions)
-  [Date extensions](./extensionstable#date-extensions)
-  [Dictionary extensions](./extensionstable#dictionary-extensions)
-  [Double extensions](./extensionstable#double-extensions)
-  [Float extensions](./extensionstable#float-extensions)
-  [Int extensions](./extensionstable#int-extensions)
-  [String extensions](./extensionstable#string-extensions)
-  [CGFloat extensions](./extensionstable#cgfloat-extensions)
-  [CGSize extensions](./extensionstable#cgsize-extensions)
-  [UIAlertController extensions](./extensionstable#uialertcontroller-extensions)
-  [UIButton extensions](./extensionstable#uibutton-extensions)
-  [UIColor extensions](./extensionstable#uicolor-extensions)
-  [UIImage extensions](./extensionstable#uiimage-extensions)
-  [UIImageView extensions](./extensionstable#uiimageview-extensions)
-  [UINavigationBar extensions](./extensionstable#uinavigationbar-extensions)
-  [UINavigationController extensions](./extensionstable#uinavigationcontroller-extensions)
-  [UISearchBar extensions](./extensionstable#uisearchbar-extensions)
-  [UILabel extensions](./extensionstable#uilabel-extensions)
-  [UITableView extensions](./extensionstable#uitableview-extensions)
-  [UITextField extensions](./extensionstable#uitextfield-extensions)
-  [UIView extensions](./extensionstable#uiview-extensions)
-  [UIViewController extensions](./extensionstable#uiviewcontroller-extensions)


## How cool is this?

Swifter Swift is a library of over **250** properties and methods, designed to extend Swift's functionality and productivity, staying faithful to the original design guidelines of swift 3.
Here are some examples:

#### Array Extensions (14)
```swift
// Remove duplicates from array
[1, 2, 3, 1, 3].removeDuplicates() -> [1, 2, 3]

// Return all indexes of specified item
["h", "e", "l", "l", "o"].indexes(of item: "l") -> [2, 3]

// Return random item from array
[1, 2, 3, 4, 5].randomItem -> 3

// and many others!
```


#### Date Extensions (28)
```swift
// Get and set components from date with ease
date.hour = 14

// Check if date is in today
Date().isInToday -> true

// Add 1 month to current date
Date().add(component: .month, value: 1)

// Return date at the beginning of current day
Date().beginning(of component: .day)

// Return date at the end of current month
Date().end(of component: .month)

// Check if date is in current calendar unit
Date().isIn(current: .month) -> true

// Return iso8601 string for date
Date().iso8601String -> "2016-08-23T21:26:15.287Z"

// Create date from iso8601 string
let date = Date(iso8601String: "2016-08-23T21:26:15.287Z")

// Create date from DateComponents
let date = Date(year: 2016, month: 8, day: 15) // other components set to current
let date = Date(hour: 9, minute: 18, second: 1) // other components set to current

// Represent date as a string with ease
Date().dateString(ofStyle: .medium) -> "Aug 26, 2016"
Date().timeString(ofStyle: .short) -> "12:55 AM"
Date().dateTimeString() -> "Aug 26, 2016, 12:55:24 AM"

// and many others!
```


#### String Extensions (53)
```swift
// Return count of substring in string
"hello world".count(of "o", caseSensitive: false) -> 2

// Return an array of strings separated by given string
"hello world".split(by separator: " ") -> ["hello", "world"]

// Return string with no spaces or new lines in beginning and end
"\n Hello   ".trimmed -> "Hello"

// Return most common character in string
"swifterSwift is making swift more swifty".mostCommonCharacter -> "i"

// Returns CamelCase of string
"Some variable name".camelCased -> "someVariableName"

// Check if string is in valid email format
"omaralbeik@gmail.com".isEmail -> true

// Check if string contains at least one letter and one number
"123abc".isAlphaNumeric -> true

// Reverse string
"123abc".reverse() -> "cba321"

// Return latinized string
"Hèllö Wórld!".latinize() -> "Hello World!"

// Return latinized string
String.random(of length: 10) -> "AhEju28kNl"

// Check if string contains one or more instance of substring
"Hello World!".contain(string: "o", caseSensitive: false) -> true

// Check if string contains one or more emojis
"string👨‍with😍emojis✊🏿".containEmoji -> true

// Convert string to numbers
"12.12".toDouble -> 12.12

// Encode and decode URLs
"it's easy to encode strings".urlEncoded -> "it's%20easy%20to%20encode%20strings"
"it's%20easy%20to%20encode%20strings".urlDecoded -> "it's easy to encode strings"

// Encode and decode base64
"Hello World!".base64Encoded -> "SGVsbG8gV29ybGQh"
"SGVsbG8gV29ybGQh".base64Decoded = "Hello World!"

// Truncate strings with a trailing
"This is a very long sentence".truncated(to length: 14, trailing: = "...") -> "This is a very..."

// Repeat a string n times
"s" * 5 -> "sssss"
// and many others!
```


#### UIColor Extensions (7)
```swift
// Create new UIColor for RGB values
let color = UIColor(red: 121, green: 220, blue: 164)

// Create new UIColor for a hexadecimal value
let color = UIColor(netHex:0x45C91B)

// Return hexadecimal value string
UIColor.red.hexString -> "#FF0000"

// Return brand colors from more than 30 social brands
let facebookColor = UIColor.socialColors.facebook

// and many others!
```


#### Number Types Extensions (33)
```swift
// Return square root of a number
√ 9 = 3

// Return square power of a number
5 ** 2 = 25

// Return a number plus or minus another number
5 ± 2 = (3, 7)

// Return random number in range
Int.randomBetween(min: 1, max: 10) = 6

// Return roman numeral for a number
134.romanNumeral = "CXXXIV"

// and many others!
```


## UI Extensions

Swifter Swift has many great UI extensions:


#### UIView Extensions
```swift
// Set title, title color and image for all states at once!
button.titleForAllStates(title: "Login")
button.titleColorForAllStates(color: UIColor.blue)
button.imageForAllStates(image: UIImage(named: "login"))

// Set borderColor, borderWidth, cornerRadius, shadowColor, and many other properties from code or storyboard
view.cornerRadius = 30
```
<p align="left">
  <img src="//raw.githubusercontent.com/omaralbeik/SwifterSwift/master/Documentation/screenshots/button_storyboard.png" title="UIButton properties from storyboard" width='250px'>
</p>

```swift
// Animate view with completion
view.fadeIn(duration: 1, completion:((Bool) -> Void)?)
view.fadeOut(duration: 1, completion:((Bool) -> Void)?)
view.rotate(byAngle 90, ofType type: .degrees, animated: true, duration: 1, completion:((Bool) -> Void)?)
view.rotate(toAngle -3, ofType type: .radians, animated: false, duration: 1, completion:((Bool) -> Void)?)
view.scale(by offset: 4, animated: true, duration:1, completion:((Bool) -> Void)?)
view.shake(direction: .horizontal, duration: 1, animationType: .easeOut)

// save screenshot of a view
let image = view.screenShot

// and many others!
```


#### UIAlertController Extensions
```swift
// Create a new alert controller from string or Error
let alert = UIAlertController(title: "Couldn't sign in", message: "Invalid username or password!")
let alert = UIAlertController(title: "Error", error: Error)

// show alert with ease
alert.show()
```


#### UIButton Extensions
```swift
// Set title, title color and image for all states at once!
button.titleForAllStates(title: "Login")
button.titleColorForAllStates(color: UIColor.blue)
button.imageForAllStates(image: UIImage(named: "login"))

// or set each of them from code or storyboard
button.titleForHighlighted = "Login"
```
<p align="left">
  <img src="//raw.githubusercontent.com/omaralbeik/SwifterSwift/blob/master/Documentation/screenshots/button_storyboard.png" title="UIButton properties from storyboard" width='250px'>
</p>


#### UIImage Extensions
```swift
// Crop images
let croppedImage = image.cropped(to CGRect)

// Create UIImage from color
let image = UIImage(color: UIColor, size: CGSize)

// scale to fit width or height
let scaledImage = image.scaledToHeight(height: CGFloat)
let scaledImage = image.scaledToWidth(height: CGFloat)
```


#### UIImageView Extensions
```swift
// Download an image from URL in background
imageView.download(from url, contentMode: .scaleAspectFit, placeHolder: UIImage?)
```


#### UINavigationBar Extensions
```swift
// Change navigation bar font and color
navbar.setTitleFont(UIFont, with color: UIColor.black)
```


#### UINavigationController Extensions
```swift
// Pop ViewController with completion handler.
navController.popViewController(completion: (()->Void)?)

// Push ViewController with completion handler.
navController.pushViewController(UIViewController, completion: (()->Void)?)
```


#### UITableView Extensions
```swift
// Return index path for last row in section.
tableView.indexPathForLastRow(in section: 2)

// Scroll to bottom or top of TableView.
tableView.scrollToBottom(animated: true)
tableView.scrollToTop(animated: true)

// and many others!
```


#### Misc Extensions
```swift
// Return JSON string from a dictionary
let jsonString = someDictionary.jsonString(prettify: true)

// Return JSON data from a dictionary
let jsonData = someDictionary.jsonData

// Check if app is running in debugging mode
swifterSwift.isInDebuggingMode

// Check if app is running on simulator
swifterSwift.isRunningOnSimulator

// and many others!
```


## Thanks:

Special thanks to:

* [Eng. Abdul Rahman Dabbour](https://github.com/thedabbour) for documenting the project

* [Mert Akengin](https://github.com/PvtMert) for creating [project website](http://swiftierswift.com) and helping with unit testing

* [John Doe](https://en.wikipedia.org/wiki/John_Doe), This is a random person of our friends who gets us some coffee day to day