# Contract
General-purpose programming language. Inspired by clean code practices and functional programming concepts.

- Protocol oriented
- No OOP
- Strict typing
- No constant variables (immutability provided via contracts itself)
- No optional values (do not have strong opinion here, still experimenting)
- Errors via exceptions

## Motivation
You can read it [here](https://github.com/ordohydra/Contract_Docs/blob/main/Motivation/motivation.md)

## Current stage
Developing Contract <-> Dart translator [here](https://github.com/ordohydra/contract)

## Syntax Example
```
# Colors

contract Color:
	func hexCode() -> Int

contract Car:
	func numberOfWheels() -> Int
	func color() -> Color

namespace Color:
	
	impl Red of Color:
		func hexCode() -> Int: # Implemetation can use function or variable with same name to satisfy contract
			return 0xFF0000

	impl Green of Color:
		var hexCode: Int = 0x00FF00

impl Mercedes of Car:
	var numberOfWheels: Int = 4

	func color() -> Color:
		return Color.Red

# Figures

contract Figure:
	func area() -> Double

impl Rect of Figure:
	init(&width Double, &height Double): # `&` symbol is used to automatically "catch" reference for variable in constructor, not to make own copies of them manually

	func area() -> Double:
		return width * height

```
## Feedback

Feedback and constructive critics are welcome
You can contact me via:

- [LinkedIn](https://www.linkedin.com/in/victor-sukochev/)
- Issues 