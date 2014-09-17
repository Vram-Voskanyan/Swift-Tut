Swift-Tut
=========

## A

### UInt
```swift
let minValue = UInt8.min  // minValue is equal to 0, and is of type UInt8
let maxValue = UInt8.max  // maxValue is equal to 255, and is of type UInt8
```

### typealias
```swift
typealias AudioSample = UInt16

var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound is now 0
```

### Tuples
```swift
let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")

let (statusCode, statusMessage) = http404Error
println("The status code is \(statusCode)")
// prints "The status code is 404"
//////////////////////////
let (justTheStatusCode, _) = http404Error
println("The status code is \(justTheStatusCode)")
// prints "The status code is 404"
//////////////////////////
println("The status code is \(http404Error.0)")
// prints "The status code is 404"
//////////////////////////
let http200Status = (statusCode: 200, description: "OK")
println("The status code is \(http200Status.statusCode)")
// prints "The status code is 200"
println("The status message is \(http200Status.description)")
// prints "The status message is OK"
```

### Assert
```swift
let age = -3
assert(age >= 0, "A person's age cannot be less than zero")
// this causes the assertion to trigger, because age is not >= 0

```

### For - > Range
```swift
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
// 1.
for i in 0..<count {
    println("Person \(i + 1) is called \(names[i])")
}
// 2.
for character in "Dog!?" {
    println(character)
}

```

## Strings
### 
```swift
var emptyString = ""               // empty string literal
var anotherEmptyString = String()  // initializer syntax
// these two strings are both empty, and are equivalent to each other
let message = "\(multiplier) times 2.5 is \(Double(multiplier) * 2.5)"
```

### Count
```swift
let unusualMenagerie = "Koala ?, Snail ?, Penguin ?, Dromedary ?"
println("unusualMenagerie has \(countElements(unusualMenagerie)) characters")

let romeoAndJuliet = [
    "Act 1 Scene 1: Verona, A public place",
    "Act 1 Scene 2: Capulet's mansion",
    "Act 1 Scene 3: A room in Capulet's mansion",
    
var act1SceneCount = 0
for scene in romeoAndJuliet {
    if scene.hasPrefix("Act 1 ") {
        ++act1SceneCount
    }
}
println("There are \(act1SceneCount) scenes in Act 1")
// prints "There are 5 scenes in Act 1"
```

## collection types
```swift
var shoppingList: [String] = ["Eggs", "Milk"]
println("The shopping list contains \(shoppingList.count) items.")
// add.
shoppingList.append("Flour")
// or
shoppingList += ["Baking Powder"]
// shoppingList now contains 4 items
shoppingList += ["Chocolate Spread", "Cheese", "Butter"]
// shoppingList now contains 7 items

// change
shoppingList[4...6] = ["Bananas", "Apples"]

// insert
shoppingList.insert("Maple Syrup", atIndex: 0)

// Remove
let mapleSyrup = shoppingList.removeAtIndex(0)
// the item that was at index 0 has just been removed
// shoppingList now contains 6 items, and no Maple Syrup
let apples = shoppingList.removeLast()


for (index, value) in enumerate(shoppingList) {
    println("Item \(index + 1): \(value)")
}
// Item 1: Six eggs
// Item 2: Milk
// Item 3: Flour
// Item 4: Baking Powder
// Item 5: Bananas

```

### Creating and Initializing an Array
```swift
var threeDoubles = [Double](count: 3, repeatedValue: 0.0)
// threeDoubles is of type [Double], and equals [0.0, 0.0, 0.0]

var anotherThreeDoubles = [Double](count: 3, repeatedValue: 2.5)
// anotherThreeDoubles is inferred as [Double], and equals [2.5, 2.5, 2.5]
 
var sixDoubles = threeDoubles + anotherThreeDoubles
// sixDoubles is inferred as [Double], and equals [0.0, 0.0, 0.0, 2.5, 2.5, 2.5]

```

### Dictionary Literals
```swift
var airports: [String: String] = ["TYO": "Tokyo", "DUB": "Dublin"]

if let oldValue = airports.updateValue("Dublin International", forKey: "DUB") {
    println("The old value for DUB was \(oldValue).")
}


```

### Control Flow
```swift

```
