# [Format Rules](https://github.com/nicklockwood/SwiftFormat/blob/master/Rules.md)

## andOperator
```swift

var x: String? = "Hello"

if x != nil && x!.isEmpty == false {}

// to

if let value = x, x.isEmpty == false {}
```

## anyObjectProtocol
```swift

private lazy var anyView: UIView = {
  let view = UIView()
  return view
}()

// to

private lazy var anyView: UIView = UIView()
```

## blankLinesAroundMark (與下方程式碼空一行)
```swift

// MARK: - Enum
enum Mode {}

// to

// MARK: - Enum

enum Mode {}
```

## blankLinesAtEndOfScope (Scope結束，移除多餘空行)
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

## blankLinesAtStartOfScope (Scope開始，移除多餘空行)
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

## blankLinesBetweenScopes
## braces
## consecutiveBlankLines

## consecutiveSpaces (移除多餘空格)
```swift
if let contentHandler = contentHandler, let bestAttemptContent =  bestAttemptContent {}

// to

if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {}
```

## elseOnSameLine
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

## emptyBraces
```swift
public init() {

}

// to

public init() {}
```

## enumNamespaces

## extensionAccessControl
```swift
extension UIGestureRecognizer {
  public func clearActionKit() {}
}

// to

public extension UIGestureRecognizer {
   func clearActionKit() {}
}
```

## fileHeader

## hoistPatternLet
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

## indent
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

## initCoderUnavailable
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

## leadingDelimiters
## linebreakAtEndOfFile
## linebreaks

## modifierOrder
```swift
private override init() {}

// to

override private init() {}

```

## numberFormatting
```swift
let range: (lower: Double, upper: Double, step: Int) = (0,#000,#00)
let color: UIColor = UIColor(netHex: 0xffffff)

// to

let range: (lower: Double, upper: Double, step: Int) = (0,#_000,#00)
let color: UIColor = UIColor(netHex: 0xFFFFFF)

```

## preferKeyPath
```swift
var array: [String] = []
array.append(contentsOf: cityModels.compactMap({ $0.name }))

// to

var array: [String] = []
array.append(contentsOf: cityModels.compactMap(\.name))

```

## redundantBackticks

## redundantBreak
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

## redundantExtensionACL

## redundantFileprivate
```swift
fileprivate func showPicker() {}

// to

private func showPicker() {}

```

## redundantGet

## redundantInit
```swift
let barItem = UIBarButtonItem.init(customView: btnItem)

// to

let barItem = UIBarButtonItem(customView: btnItem)

```

## redundantLet

```swift
let _ = 1 + 1

// to

_ = 1 + 1

```

## redundantLetError

```swift
do {
} catch let error {
}

// to

do {
} catch {
}

```

## redundantNilInit

```swift
var googleErrorHandler: ((_ errorMsg: String) -> Void)? = nil

// to

var googleErrorHandler: ((_ errorMsg: String) -> Void)?

```

## redundantObjc

## redundantParens

```swift
if (isDeleted == false) {}

// to

if isDeleted == false {}

```

## redundantPattern

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

## redundantRawValues

```swift
enum Entry: String {
  case bannerId = "bannerId"
}

// to

enum Entry: String {
  case bannerId
}

```

## redundantReturn

```swift
func numberOfItems(in carousel: iCarousel) -> Int {
  return InsiderPushNotification.getNumberOfSlide()
}

// to

func numberOfItems(in carousel: iCarousel) -> Int {
  InsiderPushNotification.getNumberOfSlide()
}

```

## redundantSelf

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

## redundantType

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

## redundantVoidReturnType

## semicolons

## sortedImports

```swift
import UIKit
import SwiftyJSON

// to

import SwiftyJSON
import UIKit

```

## spaceAroundBraces

```swift
let value = dataset.filter{ $0.type == .homeLife }.compactMap { $0.traceId }

// to

let value = dataset.filter { $0.type == .homeLife }.compactMap { $0.traceId }

```

## spaceAroundBrackets

## spaceAroundComments

```swift
if arr?.count == 0 {// 空陣列
}

// to

if arr?.count == 0 { // 空陣列
}

```

## spaceAroundGenerics

## spaceAroundOperators

```swift
static func saveMemberPhone(_ phone : String) {}

// to

static func saveMemberPhone(_ phone: String) {}

```

## spaceAroundParens

```swift
private (set) var trend: CommunityContent.Trend?

// to

private(set) var trend: CommunityContent.Trend?

```

## spaceInsideBraces

```swift
mainLayer.sublayers?.forEach({$0.removeFromSuperlayer()})

// to

mainLayer.sublayers?.forEach({ $0.removeFromSuperlayer() })

```

## spaceInsideBrackets

```swift
let array = [ "A", "B", "C" ]

// to

let array = ["A", "B", "C"]

```

## spaceInsideBrackets

```swift
//AppCore.saveHomeInfo(greetings: "", scheduleID: "")
/*case "loan":*/

// to

// AppCore.saveHomeInfo(greetings: "", scheduleID: "")
/* case "loan": */

```

## spaceInsideGenerics

## spaceInsideParens

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

## strongOutlets

```swift

@IBOutlet weak var webView: CommonWebView!

// to

@IBOutlet var webView: CommonWebView!

```

## strongifiedSelf

## todos

```swift
// MARK:- UIBarButtonItem actions

// to

// MARK: - UIBarButtonItem actions

```

## trailingClosures 

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

## trailingCommas 

```swift
let array = [1, 2, 3, 4, 5]

// to

let array = [1, 2, 3, 4, 5,]

```

## trailingCommas 

```swift
let array = [1, 2, 3, 4, 5]

// to

let array = [1, 2, 3, 4, 5,]

```

## trailingSpace(移除空格)

## typeSugar

```swift
var array: Array<Element> { map { $0 } }
var value: Dictionary<String, String>

// to

var array: [Element] { map { $0 } }
var value: [String: String]

```

## unusedArguments

```swift
func didReceive(_ notification: UNNotification) {
  InsiderPushNotification.interactivePushDidReceive()
}

// to

func didReceive(_: UNNotification) {
  InsiderPushNotification.interactivePushDidReceive()
}

```

## void

```swift
var didFinishedUpdateMessageList: (() -> ())? = nil

// to

var didFinishedUpdateMessageList: (() -> Void)? = nil

```

## wrap

## wrapArguments

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

## wrapAttributes

## wrapMultilineStatementBraces

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

## yodaConditions

```swift
if false == jsonMRT.arrayValue.isEmpty {}

// to

if jsonMRT.arrayValue.isEmpty == false {}

```

## assertionFailures
## duplicateImports
## redundantClosure
## sortDeclarations