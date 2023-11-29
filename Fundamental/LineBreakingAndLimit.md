# LineBreaking

## 기본

1. 가급적 한 줄 당 80 (또는 100자) 를 넘기지 않도록 한다.

2. 한 파일에 코드 수는 2-300자가 가장 보기 좋다.(300자를 넘기지 말라는 의미는 아님)
   다만 300자가 넘어가는 경우 기능에 따라, 중요도 따라, 접근성에 따라 파일 분리를 고민하는 것이 좋다.

4. 가독성을 위해 코드 줄 수 보다 한 줄에 작성된 코드 길이에 더 초점을 맞추고 과감하게 엔터를 누를 것

5. 생성자나 함수의 파라미터가 많아서 한줄 허용치를 넘길 경우, 괄호(`(`) 와 쉼표(`,`)를 기준으로 줄 구분을 한다.

```swift
func onTapGesture(     // 엔터
    count: Int = 1,     // 엔터
    perform action: @escaping () -> Void // 엔터
) -> some View
```

```swift
let cell = tableView.dequeueCellReusableCell(withIdentifier: .customCell, for: indexPath) as! MyCustomTableViewCell

let cell = tableView.dequeueCellReusableCell(
    withIdentifier: .customCell,
    for: indexPath
) as! MyCustomTableViewCell
```

3. 조건문이 많아서 한줄 허용치를 넘기는 경우, 쉼표를 기준으로 줄 구분을 하거나 여러개의 조건문으로 적절히 분리한다

```swift
// 조건문이 너무 많은 경우
guard message.channel == currentChannel, message.sender == me, message.isImportant, currentChannel.allowsImportantMessage else {
    return
}
showMessageAsImportant()
```
```swift
// 쉼표를 기준으로 줄 구분하기
guard message.channel == currentChannel,
    message.sender == me,
    message.isImportant,
    currentChannel.allowsImportantMessage else {
    return
}
showMessageAsImportant()
```
```swift
// 여러개의 조건문으로 적절히 분리하기
guard message.channel == currentChannel, message.sender == me else { return }
guard message.isImportant, currentChannel.allowsImportantMessage else { return }

showMessageAsImportant()
```

