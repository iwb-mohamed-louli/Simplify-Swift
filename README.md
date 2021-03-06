# Simplify-Swift

[![Version](https://img.shields.io/cocoapods/v/Simplify-Swift.svg?style=flat)](https://cocoapods.org/pods/Simplify-Swift)
[![License](https://img.shields.io/cocoapods/l/Simplify-Swift.svg?style=flat)](https://cocoapods.org/pods/Simplify-Swift)
[![Platform](https://img.shields.io/cocoapods/p/Simplify-Swift.svg?style=flat)](https://cocoapods.org/pods/Simplify-Swift)

Simplify-Swift is a high-performance Swift polyline simplification library ported from [Simplify.js](http://mourner.github.io/simplify-js/). The original Javascript library was extracted from [Leaflet](https://leafletjs.com), a JS interactive maps library by [Vladimir Agafonkin](http://agafonkin.com/en). It uses a combination of Douglas-Peucker and Radial Distance algorithms.

Polyline simplification dramatically reduces the number of points in a polyline while retaining its shape, giving a huge performance boost when processing it and also reducing visual noise. For example, it's essential when rendering a large polyline in MapKit.

![Simplify-Swift screenshot](https://raw.githubusercontent.com/tomislav/Simplify-Swift/master/screenshot.png)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Installation

Simplify-Swift is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'Simplify-Swift'
```

## Usage

```swift
class func simplify<T:SimplifyValue>(_ points: [T], tolerance: Float?, highQuality: Bool = false) -> [T]
```

Returns an array of simplified points

- parameter `points`:      An array of points of `SimplifyValue {x: Double, y: Double}` format. Generics are supported so you can pass in an array of `[CGPoint]` or `[CLLocationCoordinate2D]`.
- parameter `tolerance`:   Affects the amount of simplification (in the same metric as the point coordinates). Default: 1.
- parameter `highQuality`: Excludes distance-based preprocessing step which leads to highest quality simplification but runs ~10-20 times slower. Default: false.

## Author

Tomislav Filipcic, tf@7sols.com, [@tomislav](https://twitter.com/tomislav)

## License

Simplify-Swift is available under the MIT license. See the LICENSE file for more info.
