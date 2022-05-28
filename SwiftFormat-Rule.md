Rules = https://github.com/nicklockwood/SwiftFormat/blob/master/Rules.md

# 1. andOperator
```swift

var x: String? = "Hello"

if x != nil && x!.isEmpty == false {}

// to

if let value = x, x.isEmpty == false {}
```

# 2. anyObjectProtocol
```swift

private lazy var anyView: UIView = {
  let view = UIView()
  return view
}()

// to

private lazy var anyView: UIView = UIView()
```

# 3. blankLinesAroundMark (與下方程式碼空一行)
```swift

// MARK: - Enum
enum Mode {}

// to

// MARK: - Enum

enum Mode {}
```

# 4. blankLinesAtEndOfScope (Scope結束，移除多餘空行)
```swift
enum Mode {

  case a

  case b

}

// to

enum Mode {

  case a

  case b
}
```

# 5. blankLinesAtStartOfScope (Scope開始，移除多餘空行)
```swift
extension Mode {

  case a

  case b

}

// to

extension Mode {
  case a

  case b
}
```

# 6. blankLinesBetweenScopes
# 7. braces
# 8. consecutiveBlankLines

# 9. consecutiveSpaces (移除多餘空格)
```swift
if let contentHandler = contentHandler, let bestAttemptContent =  bestAttemptContent {}

// to

if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {}
```

# 10. elseOnSameLine
```swift
if let contentHandler = contentHandler {

}
else {
  // do...
}

// to

if let contentHandler = contentHandler {

} else {
  // do...
}
```

# 10. emptyBraces
```swift
public init() {

}

// to

public init() {}
```

# 11. enumNamespaces

# 12. extensionAccessControl
```swift
extension UIGestureRecognizer {
  public func clearActionKit() {}
}

// to

public extension UIGestureRecognizer {
   func clearActionKit() {}
}
```

# 13. fileHeader

# 14. hoistPatternLet
```swift
switch value {
  case .api(let emoji):
    break
  default:
    break  
}

// to

switch value {
  case let .api(emoji):
    break
  default:
    break  
}
```

# 15. indent
```swift
switch value {
  case .api(let emoji):
    break
  default:
    break  
}

// to

switch value {
case let .api(emoji):
  break
default:
  break  
}
```

# 16. initCoderUnavailable
```swift
open class ToolBarView: UIView {
  required public init?(coder aDecoder: NSCoder) {
    fatalError("init(coder:) has not been implemented")
  }
}

// to

open class ToolBarView: UIView {
  @available(*, unavailable)
  required public init?(coder aDecoder: NSCoder) {
    fatalError("init(coder:) has not been implemented")
  }
}

```

# 17. leadingDelimiters
# 18. linebreakAtEndOfFile
# 19. linebreaks

# 20. modifierOrder
```swift
private override init() {}

// to

override private init() {}

```

# 21. numberFormatting
```swift
let range: (lower: Double, upper: Double, step: Int) = (0, 100000, 10000)
let color: UIColor = UIColor(netHex: 0xffffff)

// to

let range: (lower: Double, upper: Double, step: Int) = (0, 100_000, 10000)
let color: UIColor = UIColor(netHex: 0xFFFFFF)

```

# 22. preferKeyPath
```swift
var array: [String] = []
array.append(contentsOf: cityModels.compactMap({ $0.name }))

// to

var array: [String] = []
array.append(contentsOf: cityModels.compactMap(\.name))

```

# 23. redundantBackticks

# 24. redundantBreak
```swift
switch value {
case "C":
  print("This is C.")
default:
  break
}

// to

switch value {
case "C":
  print("This is C.")
  break
default:
  break
}

```

# 25. redundantExtensionACL

# 26. redundantFileprivate
```swift
fileprivate func showPicker() {}

// to

private func showPicker() {}

```

# 27. redundantGet

# 28. redundantInit
```swift
let barItem = UIBarButtonItem.init(customView: btnItem)

// to

let barItem = UIBarButtonItem(customView: btnItem)

```

# 29. redundantLet

```swift
let _ = 1 + 1

// to

_ = 1 + 1

```

# 30. redundantLetError

```swift
do {
} catch let error {
}

// to

do {
} catch {
}

```

# 31. redundantNilInit

```swift
var googleErrorHandler: ((_ errorMsg: String) -> Void)? = nil

// to

var googleErrorHandler: ((_ errorMsg: String) -> Void)?

```

# 32. redundantObjc

# 33. redundantParens

```swift
if (isDeleted == false) {}

// to

if isDeleted == false {}

```

# 34. redundantPattern

```swift
switch entry {
case .myVerifyId(_):
  break
}

// to

switch entry {
case .myVerifyId:
  break
}

```

# 35. redundantRawValues

```swift
enum Entry: String {
  case bannerId = "bannerId"
}

// to

enum Entry: String {
  case bannerId
}

```

# 36. redundantReturn

```swift
func numberOfItems(in carousel: iCarousel) -> Int {
  return InsiderPushNotification.getNumberOfSlide()
}

// to

func numberOfItems(in carousel: iCarousel) -> Int {
  InsiderPushNotification.getNumberOfSlide()
}

```

# 37. redundantSelf

```swift
extension Array {

  /// 是否為空陣列
  var isNotEmpty: Bool { !self.isEmpty }
}

// to

extension Array {
  
  /// 是否為空陣列
  var isNotEmpty: Bool { !isEmpty }
}

```

# 38. redundantType

```swift
class AppCore: NSObject {

  static let shared: AppCore = AppCore()

  private init() {}
}

// to

class AppCore: NSObject {
  
  static let shared: AppCore = .init()

  private init() {}
}

```

# 39. redundantVoidReturnType

# 40. semicolons

# 41. sortedImports

```swift
import UIKit
import SwiftyJSON

// to

import SwiftyJSON
import UIKit

```

# 42. spaceAroundBraces

```swift
let value = dataset.filter{ $0.type == .homeLife }.compactMap { $0.traceId }

// to

let value = dataset.filter { $0.type == .homeLife }.compactMap { $0.traceId }

```

# 43. spaceAroundBrackets

# 44. spaceAroundComments

```swift
if arr?.count == 0 {// 空陣列
}

// to

if arr?.count == 0 { // 空陣列
}

```

# 45. spaceAroundGenerics

# 46. spaceAroundOperators

```swift
static func saveMemberPhone(_ phone : String) {}

// to

static func saveMemberPhone(_ phone: String) {}

```

# 47. spaceAroundParens

```swift
private (set) var trend: CommunityContent.Trend?

// to

private(set) var trend: CommunityContent.Trend?

```

# 48. spaceInsideBraces

```swift
mainLayer.sublayers?.forEach({$0.removeFromSuperlayer()})

// to

mainLayer.sublayers?.forEach({ $0.removeFromSuperlayer() })

```

# 49. spaceInsideBrackets

```swift
let array = [ "A", "B", "C" ]

// to

let array = ["A", "B", "C"]

```

# 50. spaceInsideBrackets

```swift
//AppCore.saveHomeInfo(greetings: "", scheduleID: "")
/*case "loan":*/

// to

// AppCore.saveHomeInfo(greetings: "", scheduleID: "")
/* case "loan": */

```

# 51. spaceInsideGenerics

# 52. spaceInsideParens

```swift
private func fetchChangePhoneNumber(attach policy: Policy,
                                    newPhone: String,
                                    secret: String ) {
}

// to

private func fetchChangePhoneNumber(attach policy: Policy,
                                    newPhone: String,
                                    secret: String) {
}

```

# 53. strongOutlets

```swift

@IBOutlet weak var webView: CommonWebView!

// to

@IBOutlet var webView: CommonWebView!

```

# 54. strongifiedSelf

# 55. todos

```swift
// MARK:- UIBarButtonItem actions

// to

// MARK: - UIBarButtonItem actions

```

# 56. trailingClosures 

```swift
extension Array where Element: Hashable {
  /// Array轉成Set
  var set: Set<Element> {
    return Set(map({ $0 }))
  }
}

// to

extension Array where Element: Hashable {
  /// Array轉成Set
  var set: Set<Element> {
    return Set(map { $0 })
  }
}

```

# 57. trailingCommas 

```swift
let array = [1, 2, 3, 4, 5]

// to

let array = [1, 2, 3, 4, 5,]

```

# 58. trailingCommas 

```swift
let array = [1, 2, 3, 4, 5]

// to

let array = [1, 2, 3, 4, 5,]

```

# 59. trailingSpace(移除空格)

# 60. typeSugar

```swift
var array: Array<Element> { map { $0 } }
var value: Dictionary<String, String>

// to

var array: [Element] { map { $0 } }
var value: [String: String]

```

# 61. unusedArguments

```swift
func didReceive(_ notification: UNNotification) {
  InsiderPushNotification.interactivePushDidReceive()
}

// to

func didReceive(_: UNNotification) {
  InsiderPushNotification.interactivePushDidReceive()
}

```

# 62. void

```swift
var didFinishedUpdateMessageList: (() -> ())? = nil

// to

var didFinishedUpdateMessageList: (() -> Void)? = nil

```

# 63. wrap

# 64. wrapArguments

```swift
sendEvent(with: event,
        parameters: [
          "sinyi_buy_property_id": houseNo.isNilSet("")
        ])

// to

sendEvent(with: event,
          parameters: [
            "sinyi_buy_property_id": houseNo.isNilSet("")
          ])

```

# 65. wrapAttributes

# 66. wrapMultilineStatementBraces

```swift
if AppCore.shared.aliveVerifyFlag != verifyFlag ||
   AppCore.shared.aliveIsDealCustomer != isDealCustomer {

}

// to

if AppCore.shared.aliveVerifyFlag != verifyFlag ||
   AppCore.shared.aliveIsDealCustomer != isDealCustomer
{

}

```

# 67. yodaConditions

```swift
if false == jsonMRT.arrayValue.isEmpty {}

// to

if jsonMRT.arrayValue.isEmpty == false {}

```

# 68. assertionFailures
# 69. duplicateImports
# 70. redundantClosure
# 71. sortDeclarations