# flutter_native_web

Native WebView as a widget in flutter

Inline WebView in flutter using [AndroidView](https://docs.flutter.io/flutter/widgets/AndroidView-class.html)

# Supported

* Android


> Note
> * Keypad is not working (No Support by flutter)
> * Don't use inside scrollview

## Screenshot

<img src="https://github.com/PonnamKarthik/FlutterWebView/raw/master/screenshots/1.png" alt="Screenshot" style="width:150px;"/>


## How to Use

```yaml

dependencies:
  flutter_native_web: "^0.1.2"
  
```

```dart

import 'package:flutter_native_web/flutterwebview.dart';

```
```dart

WebController webController;

FlutterWebView flutterWebView = new FlutterWebView(
  onWebCreated: onWebCreated,
);
```
```dart
 new Container(
    child: flutterWebViewString,
    height: 300.0,
    width: 500.0,
 ),
 ```
 ```dart
 void onWebCreated(webController) {
     this.webController = webController;
     this.webController.loadUrl("https://facebook.com");
     this.webController.onPageStarted.listen((url) =>
         print("Loading $url")
     );
     this.webController.onPageFinished.listen((url) =>
         print("Finished loading $url")
     );
 }
```

## or

 ```dart
 String html = '<body>Hello world! <a href="www.html5rocks.com">HTML5 rocks!';

 void onWebCreated(webController) {
     this.webController = webController;
     this.webController.loadData(html);
     this.webController.onPageStarted.listen((url) =>
         print("Loading $url")
     );
     this.webController.onPageFinished.listen((url) =>
         print("Finished loading $url")
     );
 }
```


### Android

Ensure the following permission is present in your Android Manifest file, located in `<project root>/android/app/src/main/AndroidManifest.xml:

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

## Coming soon

* JSInterface
* more (suggest)
