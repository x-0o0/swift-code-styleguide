# 데이터 모델

[Model Data](https://developer.apple.com/documentation/swiftui/model-data)
1. 가급적 Model, Data 가 없이 사용할 수 있는 단어를 사용할 것
```swift
@Observable class Library
```
[Managing model data in your app - Apple, Inc](https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app#:~:text=%40Observable%20class%20Library%20%7B)

2. 그 외의 경우 모델명 + `Data` 로 끝낼 것 사용
```swift
// Swift Playground - Date Planner by Apple, Inc.
class EventData: ObservableObject
```
```swift
// Updating an app to use Swift concurrency - Apple, Inc.
class CoffeeData: ObservableObject
```

## 모델 데이터 이름
데이터 모델명을 그대로 사용.

```swift
@StateObject private var library = Libaray()
```
```swift
@StateObject private var coffeeData = CoffeeData()
```

다른 데이터 모델이 없는 경우, 어떤 역할을 하는 모델 데이터인지 명확하게 알 수 있는 상황일 때 modelData 명칭을 사용해도 됨. 

```swift
@StateObject private var eventData = EventData()
@State private var event = Event()
```
