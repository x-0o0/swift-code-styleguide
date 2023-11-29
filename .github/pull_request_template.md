## 설명

### 경로 (옵셔널)

항목이 속할 파일 경로를 작성해주세요.
Fundamental/Enum

### 내용

예시: 
associated value를 사용할 때는 `let` 을 변수명 앞에 작성합니다.
```swift
- case let .success(profileImage?):
+ case .success(let profileImage?):
```



## 실제 사례
- API Design Guideline | Apple Developer Documentation 링크 (해당 문구에 대한 텍스트 하이라이트 링크를 넣어주세요)
- Xcode project 파일인 경우, 프로젝트 다운경로와 파일명과 라인을 작성해주세요

예시1: https://developer.apple.com/documentation/photokit/bringing_photos_picker_to_your_swiftui_app#:~:text=case%20.success(let%20profileImage%3F)%3A
예시2: line#17, ProfileModel.swift, https://developer.apple.com/documentation/photokit/bringing_photos_picker_to_your_swiftui_app

