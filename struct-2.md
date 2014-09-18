

### Lazy Stored Properties
A lazy stored property is a property whose initial value is not calculated until the first time it is used. 
``` swift
class DataImporter {
    var fileName = "data.txt"
}
 
class DataManager {
    lazy var importer = DataImporter()
    var data = [String]()
}
 
let manager = DataManager()
manager.data.append("Some data")
manager.data.append("Some more data")
// the DataImporter instance for the importer property has not yet been created

println(manager.importer.fileName)
// the DataImporter instance for the importer property has now been created
// prints "data.txt"

```

## Computed Properties (complex struct)
``` swift
struct Point {
    var x = 0.0, y = 0.0
}
struct Size {
    var width = 0.0, height = 0.0
}
struct Rect {
    var origin = Point()
    var size = Size()
    var center: Point {
        get {
            let centerX = origin.x + (size.width / 2)
            let centerY = origin.y + (size.height / 2)
            return Point(x: centerX, y: centerY)
        }
        set(newCenter) {
            origin.x = newCenter.x - (size.width / 2)
            origin.y = newCenter.y - (size.height / 2)
        }
    }
}
var square = Rect(origin: Point(x: 0.0, y: 0.0),
    size: Size(width: 10.0, height: 10.0))
let initialSquareCenter = square.center
square.center = Point(x: 15.0, y: 15.0)
println("square.origin is now at (\(square.origin.x), \(square.origin.y))")
```
