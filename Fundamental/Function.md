# Function

## 기본

기본적으로 함수를 명명할 때는 동사 원형으로 합니다. 하지만 값을 리턴하는 것이 목적인 경우 명사형으로 명명합니다.

```swift
// 1. 동사형 - 일반적인 경우
func remove(at position: Index) -> Element // 값을 리턴하지만 리턴이 주 목적이 아니라, 제거하는 것이 주 목적

// 2. 명사형 - 값 리턴이 목적인 경우
func cellForRow(at indexPath: IndexPath) -> UITableViewCell?
```

함수를 가진 객체가 대상이고, closure 를 실행시키는 것이 목적인 함수의 경우 함수 역할을 더 잘 전달하기 위해, on+명사 형태를 쓸 수 있습니다.

```swift
/// 자신을 호출한 뷰에 대해서, action 을 perform 하는 것이 메인 목적인 함수
func onTapGesture(
    count: Int = 1,
    perform action: @escaping () -> Void
) -> some View
```

## 상세규칙

다음과 같이 상세 규칙을 정리합니다.

### 함수에 어울리지 않는 경우
만약 다음 두 조건을 만족한다면, 함수가 아닌 computed property 를 사용하는 것을 고려해볼 것

1. 함수가 값을 리턴하는가?
2. 파라미터가 없는가?

```swift
- func getLastItem() -> Element
+ var lastItem: Element { get }
```

get, set 이름으로 시작할까 고민인데 파라미터가 필요없는 경우라면 프로퍼티에 get, set 을 정의해볼 수 있지 않은지 고민해볼 것

### 기존 객체에 영향을 주는지 안주는지에 따라 네이밍

```swift
var books: [Book] = [.어린왕자, .로빈슨크루소, .톰소여의모험]

books.sort() // books 를 정렬
let sortedBooks = books.sorted() // books 는 그대로, 정렬된 새로운 객체 리턴
```

### 함수 사용시 하나의 문장이 될 수 있도록 파라미터명을 지을 것

```swift
foods.remove(at: 0)
let cell = tableView.cellForRow(at: indexPath)
```

### closure 를 받는 경우 perform(argument 이름은 action) 또는 on+명사 형태를 파라미터로 쓸 것

```swift
onTapGesture(perform: {
  // action
})
```

```swift
doSomeNetworkRequest(onRequest:onCompletion:)
```

### 사용을 지양하는 단어

| 지양 | 권장 | 비고 |
| --- | --- | --- |
| click | tap, select | 일반적으로는 tap(예: `onTapGesture`), 만약 여러개 중에 하나를 선택하는 액션이라면 select (예: `selectItem(at:animated:scrollPosition:)`) |
| longClick, longTap | longPress | 예: `onLongPressGesture` |
| get | 명사형 이름 | 예: `cellForRow(at:)` |





