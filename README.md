# Contract
General-purpose programming language. Inspired by clean code practices and functional programming concepts.

- Protocol oriented
- No OOP
- Strict typing

## Current stage
Developing Contract <-> Dart compiler

## Example
```
contract Color:
	func hexCode() -> Int

contract Car:
	func numberOfWheels() -> Int
	func color() -> Color

namespace Color:
	
	impl Red implements Color:
		func hexCode() -> Int: // Implemetation can use function or variable with same name to satisfy contract
			return 0xFF0000

	impl Green implements Color:
		const hexCode: Int = 0x00FF00 // Both const and mutable variable satisfies contract

impl Mercedes implements Car:
	mut numberOfWheels: Int = 4 // Mutable variable

	func color() -> Color:
		return Color.Red
```
