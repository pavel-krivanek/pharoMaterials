# Basic constructs in Pharo and JavaScript

## Variables declaration
| Description                               | Pharo Code                  | JavaScript Code               |
|-------------------------------------------|-----------------------------|-------------------------------|
| Declare variable `x`                    | `\| x \|`           | `let x;`            |
| Declare variables `x`, `y`, and `z`      | `\| x y z \|`       | `let x, y, z;`      |
| Declare and assign the value 5 to `x`    |               | `let x = 5;`                  |


## Assignments
| Description                               | Pharo Code                  | JavaScript Code               |
|-------------------------------------------|-----------------------------|-------------------------------|
| Assignment                     | `:=`          | `=`            |
| Assign the value 5 to `x`                | `x := 5.`         | `x = 5;`            |
| Assign the value 6 to `x`, `y`, and `z`  | `x := y := z := 6.`         | `x = y = z = 6;`              |
| Assign the result of `(y := 6) + 1` to `x`. Assign the value 6 to `y` | `x := (y := 6) + 1.` | `let y = 6; x = y + 1;` |
| Create a new instance of the `Object` class as `x` | `x := Object new.` | `let x = new Object();` |

## Boolean values

| Description                                    | Pharo Code                      | JavaScript Code             |
|------------------------------------------------|--------------------------------|-----------------------------|
| Boolean value `true` to variable `b`           | `b := true`                     | `b = true`                  |
| Boolean value `false` to variable `b`          | `b := false`                    | `b = false`                 |

# Undefined values
| Description                                 | Pharo Code   | JavaScript Code         |
|---------------------------------------------|--------------|-------------------------|
| Value of a nil object to variable `x`      | `x := nil`   | `x = null`              |
| Value of an undefined variable to `x`       |  | `x = undefined`   |
## Numbers
| Description                                 | Pharo Code   | JavaScript Code         |
|---------------------------------------------|--------------|-------------------------|
| Integer value `1` to variable `x`              | `x := 1`                        | `x = 1`                     |
| Floating-point value `3.14` to variable `x`    | `x := 3.14`                     | `x = 3.14`                  |
| Octal value `71` to variable `x`         | `x := 8r71`                    | `x = 0o71`                  |
| Hexadecimal value `0F` to variable `x`         | `x := 16rF`                    | `x = 0x0F`                  |
| Vigesimal value of `379` to variable `x`         | `x := 20rIJ`                    |                |
| Negative value `-1` to variable `x`            | `x := -1`                       | `x = -1`                    |
| Big integer value `1234567890123456789` to variable `x` | `x := 1234567890123456789` | `x = 1234567890123456789n` |
| Scaled decimal value `3.14` | `x := 3.14s2`

## 0.30000000000000004 issue

| Description                                 | Pharo Code   | JavaScript Code         |
|---------------------------------------------|--------------|-------------------------|
| Fractions              | `(1/10) + (2/10) = (3/10)`                       |                       |
| Float numbers    | `0.1 + 0.2 = 0.30000000000000004`                     | `0.1 + 0.2 == 0.30000000000000004`                 |
| Scaled decimals       | `0.1s2 + 0.2s2 = 0.3s2`                     |                   |


## Strings, Characters, Symbols
| Description                                 | Pharo Code   | JavaScript Code         |
|---------------------------------------------|--------------|-------------------------|
| String value `'Hello'` to variable `x`         | `x := 'Hello'`                  | `x = 'Hello'`               |
| String value `'I'm here'` to variable `x`      | `x := 'I''m here'`              | `x = 'I\'m here'`           |
| Character value `A` to variable `x`            | `x := $A`                       | `x = 'A'`                   |
| Character value `' '` to variable `x`          | `x := $ `<br>`x := Character space`                        | `x = ' '`                   |
| Symbol value `#aSymbol` to variable `x`        | `x := #aSymbol`                 | `x = Symbol('aSymbol')`     |
| Array value `#(3 2 1)` to variable `x`         | `x := #(3 2 1)`                 | `x = [3, 2, 1]`             |
| Mixed-type array value `#('abc' 2 $a)` to variable `x` | `x := #('abc' 2 $a)`     | `x = ['abc', 2, 'a']`        |

## Comparisons

| Description                                       | Pharo Code                         | JavaScript Code                    |
|---------------------------------------------------|-----------------------------------|------------------------------------|
| Check if `x` is equal to `y`.                      | `(x = y)`                         | `x == y;`                         |
| Check if `x` is not equal to `y`.                  | `(x ~= y)`                        | `x !== y;`                         |
| Check if `x` is identical to `y`.                  | `(x == y)`                        | `x === y;`                         |
| Check if `x` is not identical to `y`.              | `(x ~~ y)`                        | `x !== y;`                         |
| Check if `x` is greater than `y`.                  | `(x > y)`                         | `x > y;`                           |
| Check if `x` is less than `y`.                     | `(x < y)`                         | `x < y;`                           |
| Check if `x` is greater than or equal to `y`.      | `(x >= y)`                        | `x >= y;`                          |
| Check if `x` is less than or equal to `y`.         | `(x <= y)`                        | `x <= y;`                          |

## Logical expressions

| Description                                       | Pharo Code                         | JavaScript Code                    |
|---------------------------------------------------|-----------------------------------|------------------------------------|
| Negate boolean value of `b`.                       | `b not.`                          | `!b;`                              |
| Check if both conditions are true.                 | `(x < 5) & (y > 1).`              |               |
| Check if at least one condition is true.           | `(x < 5) \| (y > 1).`              |             |
| Check if both conditions are true (lazy). | `(x < 5) and: [y > 1].`           | `(x < 5) && (y > 1);`              |
| Check if at least one condition is true (lazy). | `(x < 5) or: [y > 1].`        | `(x < 5) \|\| (y > 1);`              |
| Check if both conditions are true or both false.   |  `(x < 5) eqv: (y > 1).` <br> `(x < 5) == (y > 1).`         | `(x < 5) === (y > 1);`             |
| Check if one condition is true and the other is false. | `(x < 5) xor: (y > 1).`      | `(x < 5) !== (y > 1);`             |
| Check if `5` is between `3` and `12` (inclusive).  | `5 between: 3 and: 12.`           | `5 >= 3 && 5 <= 12;`               |

## Object type checking

| Description                                       | Pharo Code                         | JavaScript Code                    |
|---------------------------------------------------|-----------------------------------|------------------------------------|
| Get the class of object `123`. | `123 class` |  |
| Get the constructor function of an object. |  | `obj.constructor` |
| Check if `anObject` is an instance of `Person`.          | `anObject isKindOf: Person.`           | `anObject instanceof Person;`           |
| Check if `123` is of type `SmallInteger`.          | `123 isMemberOf: SmallInteger.`<br>`123 class == SmallInteger.`   | `typeof 123 === 'number';`         |
| Check if `123` responds to the message `sqrt`.     | `123 respondsTo: #sqrt.`     

## Number properties

| Description                                              | Pharo Code                                    | JavaScript Code                     |
|----------------------------------------------------------|-----------------------------------------------|-------------------------------------|
| Test if number `x` is zero.                               | `x isZero`                                    | `x === 0`                           |
| Test if number `x` is positive.                           | `x positive`                                  | `x > 0`                             |
| Test if number `x` is strictly positive (greater than 0). | `x strictlyPositive`                          | `x > 0`                             |
| Test if number `x` is negative.                           | `x negative`                                  | `x < 0`                             |
| Test if number `x` is even.                               | `x even`                                      | `(x % 2) === 0`                     |
| Test if number `x` is odd.                                | `x odd`                                       | `(x % 2) !== 0`                     |
| Test if object `x` is an integer.                         | `x isInteger`                                 | `Number.isInteger(x)`               |
| Test if object `x` is a float.                            | `x isFloat`                                   | `typeof x === 'number' && !Number.isInteger(x)` |
| Test if object `x` is a number.                           | `x isNumber`                                  | `typeof x === 'number'`             |
