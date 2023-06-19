# <p align="center">✈️ Flutter Widget</p>

### <p aligh="center">✈️ Flutter Widget</p>

[📎 Flutter widgets](https://docs.flutter.dev/ui/widgets)


|　|　|　|　|　|
|--|--|--|--|--|
|Accessibility|Animation and Motion|Assets, Images, and Icons|Async|Basics|
|Cupertino(iOS)|Input|Interaction Models|Layout|Material Components|
|Painting|Scrolling|Styling|Text|　|



### TextButton

```dart
TextButton(
    onPressed: () {
    if (_formKey.currentState!.validate()) {
        Navigator.pushNamed(context, "/home");
    }
    },
    child: Text("Login"))
```
