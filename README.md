# ShowCaseView

A Flutter package allows you to Showcase/Highlight your widgets step by step.

It is inspired from [Fluttery's Flutter challange](https://www.youtube.com/watch?v=Xm0ELlBtNWM).

## Preview

![The example app running in Android](https://github.com/simformsolutions/flutter_showcaseview/blob/master/preview/showcaseview.gif)

## Installing

1.  Add dependency to `pubspec.yaml`

    *Get the latest version in the 'Installing' tab on [pub.dev](https://pub.dev/packages/showcaseview)*

```dart
dependencies:
    showcaseview: ^0.1.2
```

2.  Import the package
```dart
import 'package:showcaseview/showcaseview.dart';
```

3. Adding a `ShowCaseWidget` widget.
```dart
ShowCaseWidget(
  child: Somewidget(),
),
```

4. Adding a `Showcase` widget.
```dart
GlobalKey _one = GlobalKey();
GlobalKey _two = GlobalKey();
GlobalKey _three = GlobalKey();

...

Showcase(
  key: _one,
  title: 'Menu',
  description: 'Click here to see menu options',
  child: Icon(
    Icons.menu,
    color: Colors.black45,
  ),
),
```

Some more optional parameters

```dart
Showcase(
  key: _two,
  title: 'Profile',
  description: 'Click here to go to your Profile',
  shapeBorder: CircleBorder(),
  showArrow: false,
  slideDuration: Duration(milliseconds: 1500),
  tooltipColor: Colors.blueGrey,
  child: ...,
),
```

5. Using a `Showcase.withWidget` widget.

```dart
Showcase.withWidget(
  key: _three,
  cHeight: 80,
  cWidth: 140,
  shapeBorder: CircleBorder(),
  container: Column(
    crossAxisAlignment: CrossAxisAlignment.start,
    children: <Widget>[
      ...
    ],
  ),
  child: ...,
),
```

6. Starting the `ShowCase`
```dart
someEvent(){
    ShowCaseWidget.startShowCase(context, [_one, _two, _three]);
}
```

If you want to start the `ShowCaseView` as soon as your UI built up then use below code.
```dart
WidgetsBinding.instance.addPostFrameCallback((_) =>
        ShowCaseWidget.startShowCase(context, [_one, _two, _three]));
```


## How to use
Check out the **example** app in the [example](example) directory or the 'Example' tab on pub.dartlang.org for a more complete example.


## Getting Started

This project is a starting point for a Dart
[package](https://flutter.dev/developing-packages/),
a library module containing code that can be shared easily across
multiple Flutter or Dart projects.

For help getting started with Flutter, view our 
[online documentation](https://flutter.dev/docs), which offers tutorials, 
samples, guidance on mobile development, and a full API reference.
