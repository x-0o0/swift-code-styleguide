# 클로져

## 선언부

### argument 이름을 정하면 클로져 사용시에 해당이름을 자동으로 사용

```swift
struct BookStore {
    var fetchBook: (_ bookName: String?, _ author: String?) async throws -> [Book]
}
```

**왜?**

사용할 때 자동으로 argument 이름을 사용하기 때문에 어떤 파라미터를 다루는 핸들러인지 파악이 쉬움

```swift
BookStore { bookName, author in
    // ...
}
```


### argument 이름이 아닌 타입으로 확인해야하는 경우, typealias 를 통해 타입 이름을 활용할 것

```swift
typealias BookName = String
typealias AuthorName = String

struct BookStore {
    var fetchBook: (BookName?, AuthorName?) async throws -> [Book]
}
```

**왜?**

```swift
BookStore(
    fetchBook: (String?, String?) async throws -> [Book]
)
```

`BookStore` 객체 생성시에 생성자에 클로져는 arg의 타입만 보여주게 된다. 엔터를 누르면 앞서 말한 것 처럼 arguement에 정의했던 이름이 자동으로 적용되지만
```swift
BookStore { bookName, author in
    // ...
}
```

`fetchBook` 이라는 파라미터명을 살리고 싶은 경우 이 상태에서 바로 사용해야한다.
```swift
BookStore(
    fetchBook: {  } 
)
```

하지만 아래와 같은 내용만 봐서는 각 argument 가 무슨 역할인지 알 수 없다.
```swift
(String?, String?) async throws -> [Book]
```

따라서 `typealias` 를 적극적으로 사용하도록 한다.

```swift
typealias BookName = String
typealias AuthorName = String

var fetchBook: (BookName?, AuthorName?) async throws -> [Book]
```

그러면 `BookStore` 객체 생성시 다음과 같이 클로져의 타입이 표시된다.
```swift
BookStore(
    fetchBook: (BookName?, AuthorName?) async throws -> [Book]
)
```
