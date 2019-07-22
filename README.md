# widget_with_codeview

A widget with side-by-side source code view. Extracted from the
[flutter-catalog](https://github.com/X-Wei/flutter_catalog/) open-source app.

<img src="https://github.com/X-Wei/flutter_catalog/blob/master/screenshots/Screenshot_1541613193.png?raw=true" width="240px" />
<img src="https://github.com/X-Wei/flutter_catalog/blob/master/screenshots/Screenshot_1541613197.png?raw=true" width="240px" />

## Usage

First make sure to add the source file to the app's assets by editing `pubspec.yaml`:

```yaml
dependencies:
  flutter:
    sdk: flutter
  widget_with_codeview: '1.0.0'
flutter:
  assets:
    # Include a single source code file:
    - lib/my_awesome_source_code.dart
    # Include all files under a subfoler by adding trailing "/":
    - lib/my_awesome_source_code_subdir/
    - ...
```

Then wrap the widget from that source file by a `WidgetWithCodeView`:

```dart
WidgetWithCodeView(
  child: MyAwesomeWidget(),
  sourceFilePath: 'lib/my_awesome_source_code.dart',
  // 1codeLinkPrefix` is optional. When it's specified, two more buttons
  // (open-code-in-browser, copy-code-link) will be added in the code view.
  codeLinkPrefix: 'https://github.com/<my_username>/<my_project>/blob/master/',
),
```

You can also choose to only show the code:

```dart
SourceCodeView(
  sourceFilePath: 'lib/my_awesome_source_code.dart',
  codeLinkPrefix: 'https://github.com/<my_username>/<my_project>/blob/master/',
),
```