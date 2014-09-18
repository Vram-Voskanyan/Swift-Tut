## TODO: Closures 

#### 1.
```swift
reversed = sorted(names, { (s1: String, s2: String) -> Bool in return s1 > s2 } )
```


## Enumeration Syntax
#### syntax
```swift
enum CompassPoint {
    case North
    case South
    case East
    case West
}
enum Planet {
    case Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune
}
var directionToHead = CompassPoint.West
directionToHead = .East
```

#### Matching Enumeration Values with a Switch Statement
```swift
directionToHead = .South
switch directionToHead {
case .North:
    println("Lots of planets have a north")
case .South:
    println("Watch out for penguins")
case .East:
    println("Where the sun rises")
case .West:
    println("Where the skies are blue")
    default:
    println("Not a safe place for humans")
}
// prints "Watch out for penguins"
```

#### Associated Values
```swift
enum Barcode {
    case UPCA(Int, Int, Int, Int)
    case QRCode(String)
}

var productBarcode = Barcode.UPCA(8, 85909, 51226, 3)
productBarcode = .QRCode("ABCDEFGHIJKLMNOP")

switch productBarcode {
case .UPCA(let numberSystem, let manufacturer, let product, let check):
    println("UPC-A: \(numberSystem), \(manufacturer), \(product), \(check).")
case .QRCode(let productCode):
    println("QR code: \(productCode).")
}
// prints "QR code: ABCDEFGHIJKLMNOP."
switch productBarcode {
case let .UPCA(numberSystem, manufacturer, product, check):
    println("UPC-A: \(numberSystem), \(manufacturer), \(product), \(check).")
case let .QRCode(productCode):
    println("QR code: \(productCode).")
}
// prints "QR code: ABCDEFGHIJKLMNOP."
```

#### Raw Values
```swift
enum ASCIIControlCharacter: Character {
    case Tab = "\t"
    case LineFeed = "\n"
    case CarriageReturn = "\r"
}
```

#### Classes and Structures
```swift
struct Resolution {
    var width = 0
    var height = 0
}
class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}
// Create Instance
let someResolution = Resolution()
let someVideoMode = VideoMode()
let vga = Resolution(width: 640, height: 480)

// usage
println("The width of someVideoMode is \(someVideoMode.resolution.width)")
// prints "The width of someVideoMode is 0"

```

#### Structures and Enumerations Are Value Types
```swift

let hd = Resolution(width: 1920, height: 1080)
// make a copy.
var cinema = hd

enum CompassPoint {
    case North, South, East, West
}
var currentDirection = CompassPoint.West
let rememberedDirection = currentDirection
currentDirection = .East
if rememberedDirection == .West {
    println("The remembered direction is still .West")
}
// prints "The remembered direction is still .West"
```
## Classes Are Reference Types, Identity Operators
Identical to (===)
Not identical to (!==)
```swift
if tenEighty === alsoTenEighty {
    println("tenEighty and alsoTenEighty refer to the same VideoMode instance.")
}
```
NOTE. 
-“Identical to” means that two constants or variables of class type refer to exactly the same class instance.
-“Equal to” means that two instances are considered “equal” or “equivalent” in value, for some appropriate meaning of “equal”, as defined by the type’s designer.

