# Contract
General-purpose programming language. Inspired by clean code practices and functional programming concepts.

- Protocol oriented
- No OOP
- Strict typing
- No constant variables (immutability provided via contracts itself)
- No optional values (do not have strong opinion here, still experimenting)
- Errors via exceptions

## Current stage
Developing Contract <-> Dart translator [here](https://github.com/ordohydra/contract)

## Syntax Example
```
contract Color:
	func hexCode() -> Int

contract Car:
	func numberOfWheels() -> Int
	func color() -> Color

namespace Color:
	
	implementation Red of Color:
		func hexCode() -> Int: // Implemetation can use function or variable with same name to satisfy contract
			return 0xFF0000

	implementation Green of Color:
		Int hexCode = 0x00FF00

implementation Mercedes of Car:
	numberOfWheels: Int = 4

	func color() -> Color:
		return Color.Red
```
## Feedback

Feedback and constructive critics are welcome
You can contact me via:

- [LinkedIn](https://www.linkedin.com/in/victor-sukochev/)
- Issues 