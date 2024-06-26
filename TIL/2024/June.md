## <p align="center">📆6/3</p>

### 오늘도 RiverPod! Refactoring time

```dart
//before
class MyStateProvider extends StateNotifier<Map<String, String>> {
  MyStateProvider() : super(MyStateProvider(
    // some thing initialize...
  )) {
    initialize();
  }

  Future<void> initialize() async {
     // api...
      state = MyClass.fromJson(result);
  }
}

// parent.dart
ref.watch(MyStateProvider.notifier).initialize();
//부모에서 이렇게 다시 한 번 호출 하고 있었다
```

```dart
//after
class MyStateProvider extends StateNotifier<MyClass> {
  MyStateProvider() : super(MyStateProvider('', '', '')) {
    _initialize();
    //private로 바꿔 내부에서만 사용하게 했다
    //그리고 초기화를 바로 진행하도록 했다.
  }

  Future<void> _initialize() async {
     // api...
      state = MyClass.fromJson(result);
  }
}

//당연히 클래스도 선언을 해야한다!
class MyClass ...
//..data
```

## <p align="center">📆6/16</p>

### copilot + mermaid , erdDiagram

```mermaid
erDiagram
    SCHOOL {
        INT grade
        INT class
        VARCHAR(50) teacher_name
        VARCHAR(50) subject
    }

    STUDENT {
        INT student_id
        INT grade
        INT class
        VARCHAR(50) student_name
    }

    SUBJECT {
        INT subject_id
        VARCHAR(50) subject_name
    }

    STUDENT ||--|| SCHOOL : "Belongs to"
    SCHOOL ||--|| SUBJECT : "Teaches"
```

## <p align="center">📆6/18</p>

### 다중 클래스

```python
class Animal:
  def eat(self):
    print('먹다')

class Wing:
  def flap(self):
    print('파닥거리다')  

class Bird(Animal, Wing):

  def fly(self):
    print ('날다')

b = Bird()
b.eat()
b.flap()
b.fly()
print(issubclass(Bird, Animal))
print(issubclass(Bird, Wing))

# 먹다
# 파닥거리다
# 날다
# True
# True
```
- 오답노트:
  - isSubClass는 내장된 함수임
  - 즉 Bird, Wing이 class인가를 확인하는 것

## <p align="center">📆6/20</p>

### 🚑 focus 해제 전 저장 이슈!

```dart
  Future<void> save() async {
    //저장하기 전 focus를 해제
    FocusScope.of(context).unfocus();
    // focus를 해제 하기 전 아래의 save 로직이 실행됨
    // 방지를 위하여 delay 사용
    await Future.delayed(Duration.zero);
    //do something foo
  }
```

## <p align="center">📆6/26</p>

### 🐍 회문이 아니면 예외 발생시키기

```python
class NotPalindromeError(Exception):

  def __init__(self):
    super().__init__(f'{word} 회문아님!')

def palindrome(word):
  reversedWord = word.lower().replace(" ", '')
  if reversedWord != reversedWord[::-1]:
    raise NotPalindromeError()
  return print(f'{reversedWord} 회문입니다!')

try:
  word = input()
  palindrome(word)
except NotPalindromeError as e:
  print(e)
# hwllo
# hwllo 회문아님!
 
# mom
# mom 회문입니다!  
```