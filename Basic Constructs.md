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

## Arithmetic expressions

| Description                               | Pharo Code                      | JavaScript Code                                      |
|------------------------------------------|----------------------------------|------------------------------------------------------|
| Add `6` and `3`.                                               | `6 + 3`                                      | `6 + 3`                                              |
| Subtract `3` from `6`.                                         | `6 - 3`                                      | `6 - 3`                                              |
| Multiply `6` and `3`.                                          | `6 * 3`                                      | `6 * 3`                                              |
| Evaluate `1 + 2 * 3` left to right (result: `7`).               | `1 + 2 * 3`                                  | `1 + 2 * 3`                                          |
| Divide `5` by `3` with fractional result.                       | `5 / 3`                                      | `5 / 3`                                              |
| Divide `5.0` by `3.0` with float result.                         | `5.0 / 3.0`                                  | `5.0 / 3.0`                                          |
| Divide `5.0` by `3.0` and truncate to integer.                   | `5.0 // 3.0`                                 | `Math.trunc(5.0 / 3.0)`                              |
| Divide `5.0` by `3.0` and return the remainder.                  | `5.0 \\ 3.0`                                 | `5.0 % 3.0`                                          |
| Negate the number `-5`.                                         | `-5`                                         | `-5`                                                 |
| Get the numeric sign of `5` (result: `1`).                      | `5 sign`                                     | `(x > 0) - (x < 0) \|\| +x`                            |
| Negate the number `5`.                                          | `5 negated`                                  | `-5`                                                 |
| Get the integer part of `1.2` (result: `1`).                     | `1.2 integerPart`                            | `Math.trunc(1.2)`                                    |
| Get the fractional part of `1.2` (result: `0.2`).                | `1.2 fractionPart`                           | `1.2 - Math.trunc(1.2)`                              |
| Get the reciprocal of `5` (result: `0.2`).                       | `5 reciprocal`                               | `1 / 5`                                              |
| Multiply `6` and `3.1` and auto-convert to float.                | `6 * 3.1`                                    | `6 * 3.1`                                            |
| Get the square of `5` (result: `25`).                            | `5 squared`                                  | `5 ** 2`                                             |
| Get the square root of `25` (result: `5`).                       | `25 sqrt`                                    | `Math.sqrt(25)`                                      |
| Raise `5` to the power of `2` (result: `25`).                    | `5 raisedTo: 2`                              | `5 ** 2`                                             |
| Raise `5` to the power of `2` using an integer (result: `25`).   | `5 raisedToInteger: 2`                       | `Math.pow(5, 2)`                                     |
| Get the exponential of `5` (result: `148.4131591025766`).        | `5 exp`                                      | `Math.exp(5)`                                        |
| Absolute value of `5` (result: `5`).                                              | `-5 abs`                                     | `Math.abs(-5)`                                       |
| Round `3.99` (result: `4`).                                     | `3.99 rounded`                               | `Math.round(3.99)`                                   |
| Truncate `3.99` (result: `3`).                                  | `3.99 truncated`                             | `Math.trunc(3.99)`                                   |
| Round `3.99` to one decimal place (result: `4.0`).              | `3.99 roundTo: 1`                            | `Number(3.99).toFixed(1)`                            |
| Truncate `3.99` to one decimal place (result: `3.9`).           | `3.99 truncateTo: 1`                         | `Math.trunc(3.99 * 10) / 10`                         |
| Truncate `3.99` (result: `3`).                                  | `3.99 floor`                                 | `Math.floor(3.99)`                                   |
| Round up `3.99` (result: `4`).                                  | `3.99 ceiling`                               | `Math.ceil(3.99)`                                    |
| Get the factorial of `5` (result: `120`).                       | `5 factorial`                                | `function factorial(n) { if (n == 1) return 1; return n * factorial(n - 1); } factorial(5)` |
| Divide `-5` by `3` and round toward zero (result: `-1`).         | `-5 quo: 3`                                  | `Math.trunc(-5 / 3)`                                 |
| Get the remainder when dividing `-5` by `3` and round toward zero (result: `-2`). | `-5 rem: 3`          | `-5 % 3`                                             |
| Get the greatest common denominator of `28` and `12` (result: `4`). | `28 gcd: 12`                               | `function gcd(a, b) { return !b ? a : gcd(b, a % b); } gcd(28, 12)` |
| Get the least common multiple of `28` and `12` (result: `84`).  | `28 lcm: 12`                                 | `(28 * 12) / function gcd(a, b) { return !b ? a : gcd(b, a % b); } (28, 12)` |
| Get the natural logarithm of `100` (result: `4.605170185988092`).| `100 ln`                                     | `Math.log(100)`                                      |
| Get the base 10 logarithm of `100` (result: `2`).                | `100 log`                                    | `Math.log10(100)`                                    |
| Get the logarithm of `100` with base `10` (result: `2`).         | `100 log: 10`                                | `Math.log(100) / Math.log(10)`                       |
| Get the floor of the logarithm of `100` with base `10` (result: `2`). | `100 floorLog: 10`                      | `Math.floor(Math.log10(100))`                        |
| Convert `180` degrees to radians (result: `3.141592653589793`). | `180 degreesToRadians`                       | `180 * Math.PI / 180`                                |
| Get the sine of `0.7` (result: `0.644217687237691`).             | `0.7 sin`                                    | `Math.sin(0.7)`                                      |
| Get the cosine of `0.7` (result: `0.7648421872844885`).         | `0.7 cos`                                    | `Math.cos(0.7)`                                      |
| Get the tangent of `0.7` (result: `0.8422883804630793`).        | `0.7 tan`                                    | `Math.tan(0.7)`                                      |
| Get the arcsine of `0.7` (result: `0.7753974966107531`).         | `0.7 arcSin`                                 | `Math.asin(0.7)`                                     |
| Get the arccosine of `0.7` (result: `0.7953988301841435`).       | `0.7 arcCos`                                 | `Math.acos(0.7)`                                     |
| Get the arctangent of `0.7` (result: `0.6107259643892086`).      | `0.7 arcTan`                                 | `Math.atan(0.7)`                                     |
| Get the maximum of `10` and `20` (result: `20`).                | `10 max: 20`                                 | `Math.max(10, 20)`                                   |
| Get the minimum of `10` and `20` (result: `10`).                | `10 min: 20`                                 | `Math.min(10, 20)`                                   |
| Get the value of pi (result: `3.141592653589793`).              | `Float pi`                                   | `Math.PI`                                            |
| Get the value of the exp constant (result: `2.718281828459045`). | `Float e`                                    | `Math.E`                                             |
| Get the value of infinity.                                      | `Float infinity`                             | `Infinity`                                           |
| Get the value of NaN (Not-a-Number).                            | `Float nan`                                  | `NaN`                                                |
| Get a random number between `0` and `1`.                        | `Random new next; yourself. x next`          | `Math.random()`                                      |
| Get a quick random number (result varies).                      | `100 atRandom`                               | `Math.floor(Math.random() * 100)`                    |

## Conversion

| Description                               | Pharo Code                      | JavaScript Code                                      |
|------------------------------------------|----------------------------------|------------------------------------------------------|
| Convert `3.99` to an integer (result: `3`).                           | `3.99 asInteger`                      | `Math.trunc(3.99)`                         |
| Convert `3.99` to a fraction (result: `399/100`).                     | `3.99 asFraction`                     | `new Fraction(3.99)`                       |
| Convert `3` to a float (result: `3.0`).                               | `3 asFloat`                           | `3.0`                                      |
| Convert the integer `65` to a character (result: `'A'`).              | `65 asCharacter`                      | `String.fromCharCode(65)`                  |
| Convert the character `'A'` to its ASCII code (result: `65`).         | `$A asciiValue`                       | `'A'.charCodeAt(0)`                        |
| Convert the object `3.99` to a string via `printOn:` (result: `'3.99'`). | `3.99 printString`                    | `String(3.99)`                             |
| Convert the object `3.99` to a string via `storeOn:` (result: `'$3.99'`). | `3.99 storeString`                    | `"$" + 3.99`                               |
| Convert `15` to a string in hexadecimal base (result: `'F'`).         | `15 radix: 16`                        | `15.toString(16).toUpperCase()`           |
| Convert `15` to a string in binary base (result: `'1111'`).            | `15 printStringBase: 2`               | `15.toString(2)`                           |

