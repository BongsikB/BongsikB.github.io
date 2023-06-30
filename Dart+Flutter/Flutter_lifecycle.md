# <p align="center">✈️ Flutter Lifecycle</p>

## ♼ 상태의 생명 주기

### StatefulWidget & StatelessWidget

### `initState()`

- `State()`객체가 생성되자 마자 가장 최초에 한 번 호출
- e.g. State가 생성되자마자 최초에 한 번 서버와 연동해 초기 데이터를 가져와서 상탯값에 할당하는 코드에 사용 가능
- 다양한 이벤트 처리 가능
- 최초 등록 후, 콜백 함수로 반복 호출 가능
    - e.g. 앱이 화면에 출력되거나 사라지는 순간에 이벤트를 처리할 때 이 리스너(옵저버)를 `initState()`함수에 등록

```dart
@override
void initState(){
  super.initState();
  controller.addListner(_prinValue);
}

@override
void dispose() {
  super.dispose();
  controller.disposer();
}
```

- `initState()` 함수에 `controller.addListner(_printValue)` → `controller` 등록된 텍스트 필드에 값이 변경될 때 마다 `_printValue` 호출→ 더 이상 필드에 값을 감지할 필요가 없을 때 `dispose()`호출

### 🏡 `build()`함수의 호출 시점

- State를 작성할 때 반드시 재정의 되어야 함
- `build()` 가 반환하는 위젯이 StatefulWidget의 화면으로 출력
- 화면을 구성할 때 호출 되는 함수


        
```dart
1. 최초 호출
2. setState() 함수에 의해 호출
3. didUpdateWidget()함수에 의해 호출
```
- `clean`: 화면이 출력 됨
    - `initState()` → `didChangeDependecies()` → `build()` 순으로 호출 되어야 출력
    - 다시 빌드 되어야하거나, 화면 갱신이 필요할 때 → State 자체의 내용변경시 상위 위젯에서 상태가 변경되어 자신에게도 반영 필요
- `State()` 자체의 내용이 변경 될 때 → `setState()` 호출
    - `Clean` → `Dirty` 상태로 변함
        - Dirty 가 된 상태 → `build()` 다시 호출하여 현재 상태로 화면을 재 출력
- `didUpdateWidget()`
    - 상위위젯의 상태 변화 → 화면을 재 빌드 시도 → 자신 & 연결된 `StatefulWidget을 다시 생성하는 순간 호출`
        - `didUpdateWidget()` 호출 → State는 자동으로 `Dirty`상태 → `build()` 호출

### 🗑️ `dispose()` 함수 호출 시점

- 상태 객체를 소멸할 때 자동으로 호출
- `dispose()` 는 최후에 한 번 호출되는 함수
    - 이벤트 리스너와 연결을 끊는 작업등을 주로 담당

---

### LifeCycle state 종류

1. `createState()`
1. `mounted == true`
1. `initState()` ✅
1. `didChangeDependencies()`
1. `build()` ✅
1. `didUpdateWidget()`
1. `setState()`
1. `deactivate()`
1. `dispose()` ✅
1. `mounted == false`



---
Ref:
- [📎 StatefulWidget lifecycle](https://flutterbyexample.com/lesson/stateful-widget-lifecycle)