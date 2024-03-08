## <p align="center">📆3/6</p>

#### build 이후에 함수 실행하기

- 비동기 작업이 필요할 때
- 프레임이 다 그려진 후 특정 처리를 하고 싶을 때
- 나는 렌더가 끝난 후, 그려진 해당 widget의 너비를 구하고자 사용했음

```dart
class _MyHomePageState extends State<MyHomePage> {
  @override
  void initState() {
    super.initState();

    WidgetsBinding.instance.addPostFrameCallback((_) async {
      //something
      _getWidth()
    });
  }
```

#### key의 currentContext 너비 얻기

```dart
  double? _getWidth() {
    if (_key.currentContext != null) {
      final RenderBox renderBox = _key.currentContext!.findRenderObject() as RenderBox;
      double width = renderBox.size.width;
      return width;
    }
    return null;
  }
```

- [addPostFrameCallback](https://api.flutter.dev/flutter/scheduler/SchedulerBinding/addPostFrameCallback.html)

#### 오랜만에 돌아온 python

```python
from requests import Response, get

results = {}

websites = (
    'google.com',
    'airbnb.com',
    'https://twitter.com',
    'facebook.com',
)

for website in websites:
  if not website.startswith('https://'):
    website = f"https://{website}"
  response = get(website)
  if response.status_code == 200:
    results[website] = 'ok'
  else:
    results[website] = 'failed'

print(results)
# 어째 일하면서 많이 본 코드다
# {'https://google.com': 'ok', 'https://airbnb.com': 'failed', 'https://twitter.com': 'failed', 'https://facebook.com': 'ok'}
```

## <p align="center">📆3/8</p>

```zsh
==> Next steps:
- Run these two commands in your terminal to add Homebrew to your PATH:
    (echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/user/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
- Run brew help to get started
- Further documentation:
    https://docs.brew.sh
```

- 무슨 말 인가 했더니..
- 터미널에 순서대로 넣어주면 되는 것이다.

```zsh
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/user/.zprofile
```

```zsh
eval "$(/opt/homebrew/bin/brew shellenv)"
```
