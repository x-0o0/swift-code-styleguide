# 용어 정리

## 뷰

### Controls
플랫폼과 컨텍스트마다 특화된 유저 인터랙션을 허용해주는 뷰. 예를 들어, 버튼, 링크, 피커가 있다.  
[Controls and indicators - Apple, Inc.](https://developer.apple.com/documentation/swiftui/controls-and-indicators?language=_5#:~:text=enable%20user%20interaction%20specific%20to%20each%20platform%20and%20context)

### Indicators
사용자에게 정보를 보여주는 뷰. 예를 들어, Progress View 와 게이지 형태가 있다.

### Field & Editor
- Field 는 편집에 대한 컨트롤 단위.
- Editor 는 편집에 대한 뷰 단위.

## 데이터 모델
데이터 모델과 모델 데이터 (Date Model & Model Data)

[Managing model data in your app - Apple, Inc.](https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app#:~:text=that%20is%2C%20an%20instance%20of%20a%20data%20model)

```swift
// Swift Playground - Date Planner by Apple, Inc.
class EventData: ObservableObject
```
1. `ObservableObject` 를 준수하여 관찰 가능한 클래스를 데이터 모델이라고 한다.
  - iOS 17, iPadOS17, macOS 14, tvOS 17, watchOS 10 부터는 `Observable()` 매크로가 적영된 클래스를 데이터 모델이라고 한다.
2. 데이터 모델의 인스턴스를 모델 데이터 라고 한다.
