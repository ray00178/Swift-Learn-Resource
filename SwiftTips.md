# Swift Tips 📚

## PropertyWrapper
```swift
@propertyWrapper
struct TextNilEmptyTo {
  private var result: String = ""
  
  var wrappedValue: String? {
    set {
      switch newValue {
      case .none:
        result = any
      case let .some(value):
        result = value.isEmpty ? any : value
      }
    }
    
    get {
      result
    }
  }
  
  private let any: String
  
  init(_ any: String) {
    self.any = any
  }
}

// MARK: - Demo

struct Demo {
  @TextNilEmptyTo("Hell")
  var room: String?
}

var demo = Demo()
demo.room = nil

// print = Hell
print("\(String(describing: demo.room))")

```