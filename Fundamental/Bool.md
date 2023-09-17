# Boolean

## 기본

Bool 타입의 변수의 명명 방식은 다음과 같이 3가지가 있다.

1. is+과거분사 형태
```swift
var isEnabled: Bool
```

2. 3인칭단수형태
```swift
var showsCancelButton: Bool
```

3. 과거분사 형태
```swift
func viewWillAppear(animated: Bool)
```

### 다이어그램
다음 순서에 따라 Bool 변수명을 짓도록 한다.
1. `@State` 이나 `@Binding` 을 사용하는가? -> 1번
2. 파라미터에 사용하는가? -> 3번
3. 설정값에 옵션을 켜는 용도인가? -> 2번
4. `SwiftUI.View` 에서 사용하는데 `@State` 이나 `@Binding` 을 사용하는 것이 아닌가? -> 2번
5. 나머지 -> 1번

## 상세설명
다음과 같이 사용 규칙을 상세하게 정리한다.

### 과거분사 형태

파라미터명에 사용.
단, argument 이름에는 `is+과거분사` 형태를 사용하거나 명명하지 않는다.

```swift
func doSomethingA(selected: Bool)

func doSomethingB(animated: Bool)

func present(_ viewController: UIViewController, animated: Bool = true)
```

### 3인칭 단수 형태

무엇의 상태가 아닌, 어떤 옵션을 켜는 등의 상태를 바꾸려는 역할을 수행하는 경우 3인칭 단수 형태를 사용
```swift
struct AppSettings {
    var showsProfileImage: Bool = false
    var enablesDarkTheme: Bool = false
    var animatesWhenLoading: Bool = false
}

let settings = AppSettings()
settings.showsProfileImage = true
settings.enablesDarkTheme = true
```

### is+과거분사 형태

위의 2가지 방식 외에 나머지 모든 경우에서는 이 형태를 사용한다. 
특히 SwiftUI 에서는 State 또는 Binding 키워드를 사용하는 변수에 is+과거분사 형태를 사용하고, 일반 변수는 3인칭 단수 형태를 쓰는 방식으로 구분한다.

```swift
struct Event {
    var endDate: Date = .now
    var isCompleted: Bool = false
    var isOutdated: Bool {
        Calendar.current.dateComponents([.month, .day], from: endDate, to: .now).day! >= 0
    }
}
```
```swift
@State private isAddingNewEvent = false
@Binding var isAddingNewEvent: Bool
```

```swift
.sheet(isPresented: $isAddingNewEvent) {
    EventEditor(event: $newEvent)
}
```
