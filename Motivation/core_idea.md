# Core idea

I am experimenting with the core idea that everything is a contract.
This will provide a "common ground" for different constructions, allowing for more flexible usage.

- A variable value can be mapped to a contract with a single function that has no arguments and returns a value of the same type.
- A type can be mapped to a contract with a single function that has no arguments and returns a value of the same type.
- A function can be mapped to a contract that contains a single function with the same arguments (the function name can be different) and the same return type.

```
contract Form:
	func area() -> Double

var calculatedArea = 42.0

func max(a: Double, b: Double) -> Double:
	if a < b:
		return b
	else:
		return a

impl Rectangle of Form:
	init(width: Double, height: Double)

	func area() -> Double:
		return width * height

var rectangle = Rectangle(20.0, 30.0)

# If we add any additional contract conformance to the Rectangle implementation,
# it will trigger an error because there will be multiple functions, and we could
# not map a single function return value to a variable.
var maxArea = max(calculatedArea, rectangle)
```

