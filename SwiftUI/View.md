# 뷰 네이밍
편집 기능이 메인인가?
- `*Editor`  
> **참고**: [Updating an app to use swift concurrency](https://developer.apple.com/documentation/swift/updating_an_app_to_use_swift_concurrency)
```swift
/// Swift Playground - Date Planner by Apple, Inc.
struct EventEditor: View { }
```

- `*EditView`
> **참고**: [Managing model data in your app - Apple, Inc.](https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app#:~:text=struct%20BookEditView%3A%20View%20%7B)
```swift
struct BookEditView: View { }
```

2. 목록에 대한 뷰인가?
- `*List`

3. 나열되는 아이템에 대한 뷰인가?
	1. 아이템이 `List` 의 row content 로 사용되는가?
		-  `*Row`
	2. 아이템이 `Grid`의 아이템으로 사용되는가?
		-  `*Column`
	3. 기타
		-  `*ItemView`
        > **참고**: [Managing model data in your app - Apple, Inc.](https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app#:~:text=of%20%60book%60%20changes.-,struct%20LibraryItemView%3A%20View%20%7B,-var%20book%3A)
        ```swift
        struct LibraryItemView: View {
        ```
