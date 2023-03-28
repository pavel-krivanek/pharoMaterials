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
| Check if `x` is equal to `y`.                      | `x = y`                         | `x == y;`                         |
| Check if `x` is not equal to `y`.                  | `x ~= y`                        | `x !== y;`                         |
| Check if `x` is identical to `y`.                  | `x == y`                        | `x === y;`                         |
| Check if `x` is not identical to `y`.              | `x ~~ y`                        | `x !== y;`                         |
| Check if `x` is greater than `y`.                  | `x > y`                         | `x > y;`                           |
| Check if `x` is less than `y`.                     | `x < y`                         | `x < y;`                           |
| Check if `x` is greater than or equal to `y`.      | `x >= y`                        | `x >= y;`                          |
| Check if `x` is less than or equal to `y`.         | `x <= y`                        | `x <= y;`                          |

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
| Test if number `x` is positive.                           | `x positive`                                  | `x >= 0`                             |
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

## Bitwise operations

| Description                                 | Pharo Code                                  | JavaScript Code                     |
|---------------------------------------------|---------------------------------------------|-------------------------------------|
| AND bits                                    | `x := 2r1111 bitAnd: 2r0100.`              | `let x = 0b1111 & 0b0100;`           |
| AND bits with different bases                | `x := 4r3333 bitAnd: 2r011011011.`         | `let x = parseInt('3333', 4) & parseInt('11011011', 2);` |
| OR bits                                     | `x := 2r1111 bitOr: 2r0100.`               | `let x = 0b1111 \| 0b0100;`          |
| XOR bits mixing bases                        | `x := 16rFF bitXor: 8r5252.`              | `let x = 0xFF ^ 0o5252;`             |
| Invert bits                                 | `x := 16rFF bitInvert.`                    | `let x = ~0xFF;`                     |
| Left shift bits                              | `x := 2r0100 bitShift: 2.`                 | `let x = 0b0100 << 2;`               |
| Right shift bits                             | `x := 2r0100 bitShift: -2.`                | `let x = 0b0100 >> 2;`               |
| Divide by four                               | `x := 2r0100 >> 2.`                        | `let x = 0b0100 >> 2;`               |
| Multiply by four                             | `x := 2r0100 << 2.`                        | `let x = 0b0100 << 2;`               |
| Bit at position (0\|1)                       | `x := 2r0100 bitAt: 3.`                    | `let x = (0b0100 & (1 << 3)) !== 0;` |
| Position of highest bit set                  | `x := 2r0100 highBit.`                     | `let x = Math.floor(Math.log2(0b0100)) + 1;` |
| Test if all bits set in mask set in receiver | `b := 16rFF allMask: 16r0F.`               | `let b = (0xFF & 0x0F) === 0x0F;`     |
| Test if any bits set in mask set in receiver | `b := 16rFF anyMask: 16r0F.`               | `let b = (0xFF & 0x0F) !== 0;`        |
| Test if all bits set in mask clear in receiver | `b := 16rFF noMask: 16r0F.`              | `let b = (0xFF & 0x0F) === 0;`        |


## Conditional statements

| Description                          | Pharo Code                                                  | JavaScript Code                                                                                     |
|--------------------------------------|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| if-then statement (with trace print) | `x > 10 ifTrue: [ 'ifTrue' traceCr ].`                       | `if (x > 10) { console.log('ifTrue'); }`                                                            |
| if-else statement (with trace print) | `x > 10 ifFalse: [ 'ifFalse' traceCr ].`                     | `if (x <= 10) { console.log('ifFalse'); }`                                                          |
| if-then-else statement                | `x > 10 ifTrue: [ 'ifTrue' traceCr ] ifFalse: [ 'ifFalse' traceCr ].` | `if (x > 10) { console.log('ifTrue'); } else { console.log('ifFalse'); }`                             |
| if-else-then statement                | `x > 10 ifFalse: [Transcript show: 'ifFalse'; cr] ifTrue: [Transcript show: 'ifTrue'; cr].` | `if (x <= 10) { console.log('ifFalse'); } else { console.log('ifTrue'); }`                            |
| if-then-else statement (with trace print) | `(x > 10 ifTrue: ['ifTrue'] ifFalse: ['ifFalse']) traceCr.` | `console.log(x > 10 ? 'ifTrue' : 'ifFalse');` 
|

## Iteration statements

| Description                          | Pharo Code                                                          | JavaScript Code                                                                     |
|--------------------------------------|---------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| while-true loop                      | `[x > 0] whileTrue: [x := x - 1. y := y * 2].`                       | `while (x > 0) { x--; y *= 2; }`                                                    |
| while-false loop                     | `[x >= 4] whileFalse: [x := x + 1. y := y * 2].`                     | `while (x < 4) { x++; y *= 2; }`                                                    |
| times-repeat loop                    | `x timesRepeat: [y := y * 2].`                                      | `for (let i = 0; i < x; i++) { y *= 2; }`                                           |
| for loop                             | `1 to: x do: [:a | y := y * 2].`                                    | `for (let a = 1; a <= x; a++) { y *= 2; }`                                          |
| for loop with specified increment    | `1 to: x by: 2 do: [:a | y := y / 2].`                              | `for (let a = 1; a <= x; a += 2) { y /= 2; }`                                       |
| iterate over array elements          | `#(5 4 3) do: [:a | x := x + a].`                                   | `const arr = [5, 4, 3]; for (let i = 0; i < arr.length; i++) { x += arr[i]; }`       |

# Strings

| Description                                 | Pharo Code                                     | JavaScript Code                                     |
|---------------------------------------------|------------------------------------------------|-----------------------------------------------------|
| Return substring                            | `x allButFirst: 10.`                           | `x.substring(10);`                                  |
| String concatenation                        | `x := 'String', 'Concatenation'.`              | `let x = 'String' + 'Concatenation';`                |
| Test if string is empty                     | `b := x isEmpty.`                             | `let b = x.length === 0;`                            |
| String size                                  | `y := x size.`                                | `let y = x.length;`                                 |
| Char at location                            | `y := x at: 2.`                               | `let y = x.charAt(1);`                               |
| First position of character within string   | `y := x indexOf: $a ifAbsent: [0].`           | `let y = x.indexOf('a'); if (y === -1) { y = 0; }`  |
| Set up to 4 elements at a time               | `x := String with: $a with: $b with: $c with: $d.` | `let x = 'abcd';`                                 |
| Iterate over the string                      | `x do: [:a | Transcript show: a printString; cr].` | `for (let i = 0; i < x.length; i++) { console.log(x.charAt(i)); }` |
| Return all elements that meet condition     | `y := x select: [:a | a > $a].`                  | `let y = x.split('').filter(char => char > 'a').join('');` |
| Convert string to symbol                     | `y := x asSymbol.`                            | `let y = Symbol(x);`                                |
| Convert string to array                      | `y := x asArray.`                             | `let y = Array.from(x);`                            |
| Convert string to byte array                 | `x := 'ABCD' asByteArray.`                    | `let x = new TextEncoder().encode('ABCD');`         |
| Convert string to ordered collection         | `y := x asOrderedCollection.`                 | `let y = new Map(); for (let i = 0; i < x.length; i++) { y.set(i, x.charAt(i)); }` |
| Convert string to sorted collection          | `y := x asSortedCollection.`                  | `let y = new Set(x); y = [...y].sort();`            |
| Convert string to bag collection             | `y := x asBag.`                               | `let y = new Map(); for (let char of x) { y.set(char, (y.get(char) || 0) + 1); }` |
| Convert string to set collection             | `y := x asSet.`                               | `let y = new Set(x);`                               |
| Randomly shuffle string                      | `y := x shuffled.`                            | `let y = x.split('').sort(() => Math.random() - 0.5).join('');` |


## Characters

| Description                         | Pharo Code                                | JavaScript Code                             |
|-------------------------------------|-------------------------------------------|---------------------------------------------|
| Character assignment                | `x := $A.`                                | `let x = 'A';`                               |
| Test if lower case                  | `y := x isLowercase.`                     | `let y = x.toLowerCase() === x;`            |
| Test if upper case                  | `y := x isUppercase.`                     | `let y = x.toUpperCase() === x;`            |
| Test if letter                      | `y := x isLetter.`                        | `let y = /^[A-Za-z]$/.test(x);`             |
| Test if digit                       | `y := x isDigit.`                         | `let y = /^[0-9]$/.test(x);`                |
| Test if alphanumeric               | `y := x isAlphaNumeric.`                  | `let y = /^[A-Za-z0-9]$/.test(x);`          |
| Test if separator character         | `y := x isSeparator.`                     | `let y = /[\s.,:;-]/.test(x);`              |
| Test if vowel                       | `y := x isVowel.`                         | `let y = /^[aeiou]$/i.test(x);`             |
| Convert to numeric digit value      | `y := x digitValue.`                      | `let y = parseInt(x);`                      |
| Convert to lower case               | `y := x asLowercase.`                     | `let y = x.toLowerCase();`                  |
| Convert to upper case               | `y := x asUppercase.`                     | `let y = x.toUpperCase();`                  |
| Convert to numeric ASCII value      | `y := x asciiValue.`                      | `let y = x.charCodeAt(0);`                  |
| Convert to string                   | `y := x asString.`                        | `let y = String(x);`                         |
| Comparison                           | `y := $A <= $B.`                          | `let y = 'A' <= 'B';`                        |
| Maximum of two characters           | `y := $A max: $B.`                        | `let y = 'A' > 'B' ? 'A' : 'B';`             |

## Symbols

| Description                              | Pharo Code                                      | JavaScript Code                                |
|------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Symbol assignment                        | `x := #Hello.`                                 | `let x = Symbol('Hello');`                     |
| Symbol concatenation (result is string)  | `y := 'String', 'Concatenation'.`              | `let y = 'String' + 'Concatenation';`          |
| Test if symbol is empty                  | `b := x isEmpty.`                             | `let b = x.description.length === 0;`         |
| Symbol size                               | `y := x size.`                                | `let y = x.description.length;`               |
| Char at location                          | `y := x at: 2.`                               | `let y = x.description.charAt(1);`            |
| Substring                                 | `y := x copyFrom: 2 to: 4.`                   | `let y = x.description.substring(1, 4);`      |
| First position of character within symbol | `y := x indexOf: $e ifAbsent: [0].`           | `let y = x.description.indexOf('e');`         |
| Iterate over the symbol                   | `x do: [:a | Transcript show: a printString; cr].` | `for (let char of x.description) { console.log(char); }` |
| Return all elements that meet condition   | `y := x select: [:a | a > $a].`               | `let y = Array.from(x.description).filter(char => char > 'a').join('');` |
| Convert symbol to string                  | `y := x asString.`                            | `let y = x.description;`                       |
| Convert symbol to text                    | `y := x asText.`                              | `let y = x.description;`                       |
| Convert symbol to array                   | `y := x asArray.`                             | `let y = Array.from(x.description);`           |
| Convert symbol to ordered collection      | `y := x asOrderedCollection.`                | `let y = new Map(); for (let i = 0; i < x.description.length; i++) { y.set(i, x.description.charAt(i)); }` |
| Convert symbol to sorted collection       | `y := x asSortedCollection.`                 | `let y = new Set(x.description); y = [...y].sort();` |
| Convert symbol to bag collection          | `y := x asBag.`                               | `let y = new Map(); for (let char of x.description) { y.set(char, (y.get(char) || 0) + 1); }` |
| Convert symbol to set collection          | `y := x asSet.`                               | `let y = new Set(x.description);`              |

## Array: Fixed length collection

| Description                                  | Pharo Code                                                  | JavaScript Code                                             |
|----------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------|
| Constant byte array                          | `x := #[255 255 255].`                                      | `let x = Uint8Array.of(255, 255, 255);`                     |
| Literal array                                | `x := #(4 3 2 1).`                                          | `let x = [4, 3, 2, 1];`                                     |
| Literal array whose first element is an array of size 3 | `x := #((1 + 2) . 3).`                            | `let x = [[1 + 2, 3]];`                                     |
| Dynamic array                                | `x := { 5. 2 * 2 + 1 . 3+2 . 8 - 3 }.`                       | `let x = [5, 2 * 2 + 1, 3 + 2, 8 - 3];`                      |
| Create array with up to 4 elements           | `x := Array with: 5 with: 4 with: 3 with: 2.`               | `let x = [5, 4, 3, 2];`                                     |
| Allocate an array with specified size        | `x := Array new: 4.`                                        | `let x = new Array(4);`                                     |
| Set array elements                           | `x at: 1 put: 5; at: 2 put: 4; at: 3 put: 3; at: 4 put: 2.` | `x[0] = 5; x[1] = 4; x[2] = 3; x[3] = 2;`                   |
| Test if array is empty                       | `b := x isEmpty.`                                           | `let b = x.length === 0;`                                    |
| Array size                                   | `y := x size.`                                              | `let y = x.length;`                                          |
| Get array element at index                   | `y := x at: 4.`                                             | `let y = x[3];`                                              |
| Test if element is in array                  | `b := x includes: 3.`                                       | `let b = x.includes(3);`                                     |
| Subarray                                     | `y := x copyFrom: 2 to: 4.`                                 | `let y = x.slice(1, 4);`                                     |
| First position of element within array       | `y := x indexOf: 3 ifAbsent: [0].`                          | `let y = x.indexOf(3) === -1 ? 0 : x.indexOf(3);`            |
| Number of times object in collection         | `y := x occurrencesOf: 3.`                                  | `let y = x.filter(element => element === 3).length;`        |
| Iterate over the array                        | `x do: [:a | Transcript show: a printString; cr].`          | `x.forEach(element => { console.log(element); });`          |
| Return collection of elements that pass test | `y := x select: [:a | a > 2].`                              | `let y = x.filter(element => element > 2);`                  |
| Return collection of elements that fail test | `y := x reject: [:a | a < 2].`                              | `let y = x.filter(element => element >= 2);`                 |
|
| Return collection of elements that fail test             | `y := x reject: [:a \| a < 2].`                        | `const y = x.filter(a => a >= 2);`                       |
| Transform each element for new collection                | `y := x collect: [:a \| a + a].`                       | `const y = x.map(a => a + a);`                           |
| Find position of first element that passes test          | `y := x detect: [:a \| a > 3] ifNone: [].`             | `const y = x.find(a => a > 3) || [];`                    |
| Sum array elements                                       | `sum := 0. x do: [:a \| sum := sum + a]. sum.`         | `let sum = 0; for (let a of x) { sum += a; }`            |
| Sum array elements                                       | `sum := 0. 1 to: (x size) do: [:a \| sum := sum + (x at: a)].` | `let sum = x.reduce((acc, val) => acc + val, 0);`         |
| Sum array elements                                       | `sum := x inject: 0 into: [:a :c \| a + c].`           | `const sum = x.reduce((acc, val) => acc + val, 0);`       |
| Find max element in array                                | `max := x inject: 0 into: [:a :c \| (a > c)`           | `const max = x.reduce((acc, val) => acc > val ? acc : val, 0);` |
| Randomly shuffle collection                              | `y := x shuffled.`                                    | `const y = x.sort(() => Math.random() - 0.5);`           |
| Convert to array                                        | `y := x asArray.`                                     | `const y = Array.from(x);`                              |
| Convert to byte array                                   | `y := x asByteArray.`                                 | Not directly supported in JavaScript.                    |
| Convert to word array                                   | `y := x asWordArray.`                                 | Not directly supported in JavaScript.                    |
| Convert to ordered collection                           | `y := x asOrderedCollection.`                         | Not directly supported in JavaScript.                    |
| Convert to sorted collection                            | `y := x asSortedCollection.`                          | `const y = Array.from(x).sort();`                        |
| Convert to bag collection                               | `y := x asBag.`                                       | Not directly supported in JavaScript.                    |
| Convert to set collection                               | `y := x asSet.`                                       | `const y = new Set(x);`                                  |

## SortedCollection

| Description                                             | Pharo Code                                                      | JavaScript Code                                       |
|---------------------------------------------------------|-----------------------------------------------------------------|-------------------------------------------------------|
| Create collection with up to 4 elements                  | `x := SortedCollection with: 4 with: 3 with: 2 with: 1.`        | `const x = [4, 3, 2, 1]; x.sort();`                   |
| Allocate collection                                      | `x := SortedCollection new.`                                  | `const x = []`                                        |
| Set sort criteria                                        | `x := SortedCollection sortBlock: [:a :c \| a > c].`           | `const x = []; x.sort((a, b) => b - a);`              |
| Add element to collection                                | `x add: 3; add: 2; add: 1; add: 4; yourself.`                 | `x.push(3); x.push(2); x.push(1); x.push(4);`          |
| Remove first element in collection                       | `y := x removeFirst.`                                          | `const y = x.shift();`                                |
| Add element at end of collection                         | `y := x addLast: 5.`                                           | `x.push(5); const y = x;`                             |
| Remove last element in collection                        | `y := x removeLast.`                                           | `const y = x.pop();`                                  |
| Add multiple elements to collection                      | `y := x addAll: #(6 7 8).`                                     | `x.push(6, 7, 8); const y = x;`                       |
| Remove multiple elements from collection                 | `y := x removeAll: #(6 7 8).`                                  | `x = x.filter(num => ![6, 7, 8].includes(num)); const y = x;` |
| Remove element from collection                           | `y := x remove: 5 ifAbsent: [].`                               | `const idx = x.indexOf(5); if (idx !== -1) { x.splice(idx, 1); } const y = x;` |
| Test if empty                                            | `b := x isEmpty.`                                              | `const b = x.length === 0;`                           |
| Number of elements                                       | `y := x size.`                                                 | `const y = x.length;`                                 |
| Retrieve element at index                                | `y := x at: 2.`                                                | `const y = x[1];`                                     |
| Retrieve first element in collection                     | `y := x first.`                                                | `const y = x[0];`                                     |
| Retrieve last element in collection                      | `y := x last.`                                                 | `const y = x[x.length - 1];`                          |
| Test if element is in collection                         | `b := x includes: 4.`                                          | `const b = x.includes(4);`                            |
| Subcollection                                            | `y := x copyFrom: 2 to: 3.`                                    | `const y = x.slice(1, 3);`                            |
| First position of element within collection              | `y := x indexOf: 3 ifAbsent: [0].`                             | `const y = x.indexOf(3) !== -1 ? x.indexOf(3) : 0;`   |
| Number of times object in collection                      | `y := x occurrencesOf: 3.`                                     | `const y = x.filter(num => num === 3).length;`        |
| Iterate over the collection                             | `x do: [:a \| Transcript show: a printString; cr].`              | `for (let a of x) { console.log(a); }`                       |
| Test if all elements meet condition                      | `b := x conform: [:a \| (a >= 1) & (a <= 4)].`                  | `const b = x.every(num => num >= 1 && num <= 4);`            |
| Return collection of elements that pass test             | `y := x select: [:a \| a > 2].`                                  | `const y = x.filter(num => num > 2);`                         |
| Return collection of elements that fail test             | `y := x reject: [:a \| a < 2].`                                  | `const y = x.filter(num => num >= 2);`                        |
| Transform each element for new collection                | `y := x collect: [:a \| a + a].`                                 | `const y = x.map(num => num + num);`                          |
| Find position of first element that passes test          | `y := x detect: [:a \| a > 3] ifNone: [].`                       | `const y = x.find(num => num > 3) || [];`                     |
| Sum elements                                             | `sum := 0. x do: [:a \| sum := sum + a]. sum.`                   | `let sum = 0; for (let a of x) { sum += a; }`                 |
| Sum elements                                             | `sum := 0. 1 to: (x size) do: [:a \| sum := sum + (x at: a)].`   | `let sum = x.reduce((acc, val) => acc + val, 0);`              |
| Sum elements                                             | `sum := x inject: 0 into: [:a :c \| a + c].`                     | `const sum = x.reduce((acc, val) => acc + val, 0);`            |
| Find max element in collection                           | `max := x inject: 0 into: [:a :c \| (a > c)`                     | `const max = x.reduce((acc, val) => acc > val ? acc : val, 0);` |
| Convert to array                                        | `y := x asArray.`                                               | `const y = Array.from(x);`                                    |
| Convert to ordered collection                           | `y := x asOrderedCollection.`                                   | Not directly supported in JavaScript.                          |
| Convert to sorted collection                            | `y := x asSortedCollection.`                                    | `const y = Array.from(x); y.sort();`                           |
| Convert to bag collection                               | `y := x asBag.`                                                 | Not directly supported in JavaScript.                          |
| Convert to set collection                               | `y := x asSet.`                                                 | `const y = new Set(x);`                                        |

## Internal Stream

| Description                                             | Pharo Code                                                      | JavaScript Code                                                         |
|---------------------------------------------------------|-----------------------------------------------------------------|-------------------------------------------------------------------------|
| Create a read stream                                    | `ios := ReadStream on: 'Hello read stream'.`                    | `const ios = new ReadableStream('Hello read stream');`                  |
| Create a read stream from a substring                    | `ios := ReadStream on: 'Hello read stream' from: 1 to: 5.`       | `const ios = new ReadableStream('Hello read stream'.substring(0, 5));`  |
| Iterate over the stream until the end                    | `[ (x := ios nextLine) notNil ] whileTrue: [ x traceCr ].`      | `let x; while (x = ios.readLine()) { console.log(x); }`                 |
| Set the position of the read stream                      | `ios position: 3.`                                              | `ios.seek(3);`                                                          |
| Get the position of the read stream                      | `ios position.`                                                 | `const pos = ios.getPosition();`                                       |
| Get the next byte from the read stream                   | `x := ios next.`                                                | `const x = ios.readByte();`                                             |
| Peek at the next byte in the read stream                 | `x := ios peek.`                                                | `const x = ios.peekByte();`                                             |
| Get the entire contents of the read stream               | `x := ios contents.`                                            | Not directly supported in JavaScript.                                    |
| Test if the end of the read stream has been reached       | `b := ios atEnd.`                                               | `const b = ios.endOfStream();`                                          |
| Create a read-write stream                               | `ios := ReadWriteStream on: 'Hello read stream'.`               | `const ios = new ReadWriteStream('Hello read stream');`                 |
| Create a read-write stream from a substring               | `ios := ReadWriteStream on: 'Hello read stream' from: 1 to: 5.`  | `const ios = new ReadWriteStream('Hello read stream'.substring(0, 5));` |
| Create a read-write stream with initial contents          | `ios := ReadWriteStream with: 'Hello read stream'.`             | `const ios = new ReadWriteStream('Hello read stream'); ios.write('Hello read stream');` |
| Create a read-write stream with initial contents          | `ios := ReadWriteStream with: 'Hello read stream' from: 1 to: 10.` | `const ios = new ReadWriteStream('Hello read stream'.substring(0, 10));` |
| Set the position of the read-write stream                 | `ios position: 0.`                                              | `ios.seek(0);`                                                          |
| Iterate over the read-write stream until the end          | `[ (x := ios nextLine) notNil ] whileTrue: [ x traceCr ].`      | `let x; while (x = ios.readLine()) { console.log(x); }`                 |
| Set the position of the read-write stream                 | `ios position: 6.`                                              | `ios.seek(6);`                                                          |
| Get the position of the read-write stream                 | `ios position.`                                                 | `const pos = ios.getPosition();`                                       |
| Write a string to the read-write stream                   | `ios nextPutAll: 'Chris'.`                                       | `ios.write('Chris');`                                                   |
| Get the next byte from the read-write stream              | `x := ios next.`                                                | `const x = ios.readByte();`                                             |
| Peek at the next byte in the read-write stream           | `x := ios peek.`                                                | `const x = ios.peekByte();`                                             |
| Get the entire contents of the read-write stream         | `x := ios contents.`                                            | Not directly supported in JavaScript.                                    |
| Test if the end of the read-write stream has been reached | `b := ios atEnd.`                                               | `const b = ios.endOfStream();`                                          |

| Creating a file                                     | `file := File named: 'asd.txt' asFileReference fullName.`                    | Not directly supported in JavaScript.                                        |
| Opening the file                                    | `file open.`                                                                  | Not directly supported in JavaScript.                                        |
| Opening the file for appending                      | `file openForAppend.`                                                         | Not directly supported in JavaScript.                                        |
| Closing the file                                    | `file close.`                                                                 | Not directly supported in JavaScript.                                        |
| Get the size of the file                             | `file size.`                                                                 | Not directly supported in JavaScript.                                        |
| Get the current position in the file                | `file position.`                                                             | Not directly supported in JavaScript.                                        |
| Set the current position in the file                | `file position: 0.`                                                           | Not directly supported in JavaScript.                                        |
| Seek to an absolute position in the file             | `file seekAbsolute: 10.`                                                      | Not directly supported in JavaScript.                                        |
| Seek to a relative position in the file              | `file seekRelative: 10.`                                                      | Not directly supported in JavaScript.                                        |
| Check if the end of the file has been reached        | `file atEnd.`                                                                 | Not directly supported in JavaScript.                                        |
| Write a string to the file                           | `file nextPutAll: 'sdd'.`                                                     | Not directly supported in JavaScript.                                        |
| Read a specified number of bytes from the file        | `file next: 2.`                                                               | Not directly supported in JavaScript.                                        |
| Buffered write                                      | `file next: 2 putAll: 'abc' startingAt: 2.`                                    | Not directly supported in JavaScript.                                        |
| Buffered read                                       | `buffer := ByteArray new: 5.`<br>`file readInto: buffer startingAt: 1 count: 5.`<br>`buffer asString.` | Not directly supported in JavaScript.                            
 Read a specified number of bytes into a buffer       | `file readInto: buffer startingAt: 1 count: 5.`<br>`buffer asString.`        | Not directly supported in JavaScript.                                        |
 
 ## File Reference
 
 | Get a handle to the user's home directory              | `p := FileLocator home.`                                                                                   | Not directly supported in JavaScript.                                      |
| Get a handle to the root of the file system            | `p := FileLocator root.`                                                                                   | Not directly supported in JavaScript.                                      |
| Get the file path string of the handle                 | `p pathString.`                                                                                            | Not directly supported in JavaScript.                                      |
| Get the path of the parent folder of the handle        | `p parent pathString.`                                                                                     | Not directly supported in JavaScript.                                      |
| Get a handle to a folder in the user's home directory  | `m := FileLocator home / 'Music'.`                                                                          | Not directly supported in JavaScript.                                      |
| Test if the folder/file represented by the handle exists | `m exists.`                                                                                              | Not directly supported in JavaScript.                                      |
| Test if the handle represents a folder                  | `m isDirectory.`                                                                                          | Not directly supported in JavaScript.                                      |
| Find all files in the folder matching a pattern         | `m allChildrenMatching: '.mp3'.`                                                                           | Not directly supported in JavaScript.                                      |
| Get a handle to a file                                 | `p := 'pharo5.image' asFileReference.`                                                                     | Not directly supported in JavaScript.                                      |
| Test if the handle represents a file                   | `p isFile.`                                                                                                | Not directly supported in JavaScript.                                      |
| Get the file name without the path                      | `p basename.`                                                                                              | Not directly supported in JavaScript.                                      |
| Write to a file                                        | `hello := 'hello.txt' asFileReference.`<br>`hello writeStreamDo: [ :stream |`<br>`stream nextPutAll: 'Hello World'].` | Not directly supported in JavaScript.                                 |
| Read from a file                                        | `hello readStreamDo: [ :stream | stream contents ].`                                                     | Not directly supported in JavaScript.                                      |

## Date

| Description                                         | Pharo Code                                                           | JavaScript Code                                                     |
|-----------------------------------------------------|----------------------------------------------------------------------|----------------------------------------------------------------------|
| Create a date object for today                      | `x := Date today.`                                                   | `const x = new Date();`                                             |
| Create a date object from the current date/time     | `x := Date dateAndTimeNow.`                                           | `const x = new Date();`                                             |
| Create a date object from a formatted string         | `x := Date readFromString: '01/02/1999'.`                             | Not directly supported in JavaScript.                                |
| Create a date object from parts                       | `x := Date newDay: 12 month: #July year: 1999.`                      | Not directly supported in JavaScript.                                |
| Create a date object from elapsed days since 1/1/1901 | `x := Date fromDays: 36000.`                                         | Not directly supported in JavaScript.                                |
| Get the day of the week as an integer                 | `y := Date dayOfWeek: #Monday.`                                      | Not directly supported in JavaScript.                                |
| Get the month of the year as an integer                | `y := Date indexOfMonth: #January.`                                 | Not directly supported in JavaScript.                                |
| Get the number of days in a specific month for a year  | `y := Date daysInMonth: 2 forYear: 1996.`                            | Not directly supported in JavaScript.                                |
| Get the number of days in a year                       | `y := Date daysInYear: 1996.`                                        | Not directly supported in JavaScript.                                |
| Get the name of the weekday                            | `y := Date nameOfDay: 1.`                                            | Not directly supported in JavaScript.                                |
| Get the name of the month                              | `y := Date nameOfMonth: 1.`                                          | Not directly supported in JavaScript.                                |
| Get the day of the week for a specific date             | `y := x weekday.`                                                   | `const y = x.getDay();`                                             |
| Get the date for the previous day of the week          | `y := x previous: #Monday.`                                          | Not directly supported in JavaScript.                                |
| Get the day of the month                                | `y := x dayOfMonth.`                                                | `const y = x.getDate();`                                            |
| Get the day of the year                                | `y := x day.`                                                       | Not directly supported in JavaScript.                                |
| Get the day of the year for the first day of month | `y := x firstDayOfMonth.`                                   | Not directly supported in JavaScript.                                |
| Get the name of the month                           | `y := x monthName.`                                         | Not directly supported in JavaScript.                                |
| Get the index of the month                          | `y := x monthIndex.`                                        | `const y = x.getMonth() + 1;`                                       |
| Get the number of days in the month                  | `y := x daysInMonth.`                                       | Not directly supported in JavaScript.                                |
| Get the year                                         | `y := x year.`                                              | `const y = x.getFullYear();`                                        |
| Get the number of days in the year                    | `y := x daysInYear.`                                        | Not directly supported in JavaScript.                                |
| Get the number of days left in the year              | `y := x daysLeftInYear.`                                    | Not directly supported in JavaScript.                                |
| Get the number of seconds elapsed since 1/1/1901    | `y := x asSeconds.`                                        | Not directly supported in JavaScript.                                |
| Add days to a date object                             | `y := x addDays: 10.`                                      | `x.setDate(x.getDate() + 10);`                                      |
| Subtract days from a date object                      | `y := x subtractDays: 10.`                                 | `x.setDate(x.getDate() - 10);`                                      |
| Subtract two date objects, result in days            | `y := x subtractDate: (Date today).`                        | Not directly supported in JavaScript.                                |
| Print formatted date                                | `y := x printFormat: #(2 1 3 $/ 1 1).`                       | `x.toLocaleDateString('en-US', { month: '2-digit', day: '2-digit', year: 'numeric' });` |
| Compare two date objects                            | `b := (x <= Date today).`                                   | `const b = (x <= new Date());`                                      |

## Time

| Description                                        | Pharo Code                                                     | JavaScript Code                                                     |
|----------------------------------------------------|----------------------------------------------------------------|----------------------------------------------------------------------|
| Create time from current time                      | `x := Time now.`                                               | `const x = new Date();`                                             |
| Create time from current time/date                 | `x := Time now asdateAndTime.`                                 | Not directly supported in JavaScript.                                |
| Create time from formatted string                  | `x := Time readFromString: '3:47:26 pm'.`                      | Not directly supported in JavaScript.                                |
| Create time from elapsed time from midnight         | `x := Time fromSeconds: 60 * 60 * 4.`                          | Not directly supported in JavaScript.                                |
| Milliseconds since midnight                        | `y := Time millisecondClockValue.`                             | `const y = Date.now() % (24 * 60 * 60 * 1000);`                     |
| Total seconds since 1/1/1901                       | `y := Time totalSeconds.`                                      | Not directly supported in JavaScript.                                |
| Seconds past minute (0-59)                         | `y := x seconds.`                                              | `const y = x.getSeconds();`                                         |
| Minutes past hour (0-59)                           | `y := x minutes.`                                              | `const y = x.getMinutes();`                                         |
| Hours past midnight (0-23)                         | `y := x hours.`                                                | `const y = x.getHours();`                                           |
| Add time to time object                            | `y := x addTime: Time now.`                                    | Not directly supported in JavaScript.                                |
| Subtract time to time object                       | `y := x subtractTime: (Time now).`                             | Not directly supported in JavaScript.                                |
| Convert time to seconds                            | `y := x asSeconds.`                                            | `const y = (x.getHours() * 60 * 60) + (x.getMinutes() * 60) + x.getSeconds();` |
| Timing facility                                    | `x := Time millisecondsToRun: [1 to: 1000 do: [:index | y := 3.14 * index]].` | Not directly supported in JavaScript.                                |
| Compare two time objects                           | `b := x <= Time now.`                                          | `const b = (x <= new Date());`                                      |

## Points

| Description                               | Pharo Code                                | JavaScript Code       |
|-------------------------------------------|-------------------------------------------|-----------------------|
| Obtain a new point                         | `pt := 200@100.`                          | -                     |
| Obtain the x coordinate of the point       | `x := pt x.`                              | -                     |
| Obtain the y coordinate of the point       | `y := pt y.`                              | -                     |
| Negate the x and y coordinates of the point | `pt := 200@100 negated.`                  | -                     |
| Obtain the absolute value of the x and y coordinates | `pt := (-200@ -100) abs.`       | -                     |
| Round the x and y coordinates of the point | `pt := (200.5@100.5) rounded.`            | -                     |
| Truncate the x and y coordinates of the point | `pt := (200.5@100.5) truncated.`      | -                     |
| Add a scale of 100 to both coordinates      | `pt := 200@100 + 100.`                    | -                     |
| Subtract a scale of 100 from both coordinates | `pt := 200@100 - 100.`                 | -                     |
| Multiply both coordinates by a scale of 2  | `pt := 200@100 * 2.`                      | -                     |
| Divide both coordinates by a scale of 2    | `pt := 200@100 / 2.`                      | -                     |
| Divide both coordinates by a scale of 2, discarding the remainder | `pt := 200@100 // 2.` | -                  |
| Obtain the remainder of dividing both coordinates by a scale of 3 | `pt := 200@100 \\ 3.` | -                 |
| Add two points together                     | `pt := (200@100) + (50@25).`              | -                     |
| Subtract one point from another             | `pt := (200@100) – (50@25).`              | -                     |
| Multiply one point by another               | `pt := (200@100) * (3@4).`                | -                     |
| Divide one point by another                 | `pt := (200@100) // (3@4).`               | -                     |
| Obtain the maximum x and y coordinates between two points | `pt := 200@100 max: 50@200.` | -      |
| Obtain the minimum x and y coordinates between two points | `pt := 200@100 min: 50@200.` | -      |
| Obtain the dot product of two points        | `pt := 20@5 dotProduct: 10@2.`            | -                     |


## Exceptions

| Description                               | Pharo Code                                                  | JavaScript Code |
|-------------------------------------------|-------------------------------------------------------------|-----------------|
| Install an exception handler for ZeroDivide exception | `[ 1/0 ] on: ZeroDivide do: [ :ex \| ... ex ... ].` | -     |
| Raise a warning signal with a message      | `Warning signal: 'watch out!'.`                              | -               |
| Always execute a block of code after a main block, even if an exception occurs | `[ 1/0 ] ensure: [ 'exception' trace].`             | -               |
| Execute a block of code only if the main block is curtailed (i.e. fails or is unwound) | `[ 1/0 ] ifCurtailed: [ Transcript show: 'exception' ].` | -        |

| Description                               | Pharo Code                                            | JavaScript Code |
|-------------------------------------------|-------------------------------------------------------|-----------------|
| Browse a specified class                   | `String browse.`                                      | -               |
| Open an object inspector window for `x`    | `x inspect.`                                          | -               |
| Display a confirmation dialog with message `Is this correct?` for `x` and return `true` or `false` | `x confirm: 'Is this correct?'.` | - |
| Set a breakpoint at `x` and open debugger window when reached | `x halt.`                                      | -               |
| Set a breakpoint at `x` with message `Halt message` and open debugger window when reached | `x halt: 'Halt message'.` | - |
| Display a notification dialog with message `Notify text` for `x` | `x notify: 'Notify text'.` | - |
| Display an error dialog with title `Error string` for `x` | `x error: 'Error string'.`                            | -               |
| Raise a `MessageNotUnderstood` exception for `x` with message selector `#cmrMessage` | `x doesNotUnderstand: #cmrMessage.` | -  |
| Raise a `ShouldNotImplement` exception for `x` | `x shouldNotImplement.`                              | -               |
| Raise a `SubclassResponsibility` exception for `x` | `x subclassResponsibility.`                     | -               |
| Raise an `ImproperStore` exception for `x` | `x errorImproperStore.`                                | -               |
| Raise a `NonIntegerIndex` exception for `x` | `x errorNonIntegerIndex.`                          | -               |
| Raise a `SubscriptOutOfBounds` exception for `x` | `x errorSubscriptBounds.`                          | -               |
| Raise a `PrimitiveFailed` exception for `x`  | `x primitiveFailed.`                                 | -               |

## STDIO

| Description                               | Pharo Code                                      | JavaScript Code                                           |
|-------------------------------------------|-------------------------------------------------|-----------------------------------------------------------|
| Output a string to internal log            | `'Hello World' trace.`                          | -                                                         |
| Output a string to external log            | `Stdio stdout nextPutAll: 'Hello world'.`       | `console.log('Hello world');`                             |

## Classes and Metaclasses

| Description                               | Pharo Code                                             | JavaScript Code |
|-------------------------------------------|--------------------------------------------------------|-----------------|
| Obtain the name of the `String` class      | `x := String name.`                                    | -               |
| Obtain the organization category of the `String` class | `x := String category.`                    | -               |
| Obtain the class comment for the `String` class | `x := String comment.`                        | -               |
| Obtain the type of subclass for the `String` class (e.g. `variableSubclass`) | `x := String kindOfSubclass.` | -        |
| Obtain the class definition for the `String` class | `x := String definition.`                        | -               |
| Obtain the names of the immediate instance variables for the `String` class | `x := String instVarNames.` | -             |
| Obtain the names of all instance variables for the `String` class (including those inherited from superclasses) | `x := String allInstVarNames.` | - |
| Obtain the names of the immediate class variables for the `String` class | `x := String classVarNames.` | -             |
| Obtain the names of all class variables for the `String` class (including those inherited from superclasses) | `x := String allClassVarNames.` | - |
| Obtain the names of the immediate shared pools (dictionaries) used by the `String` class | `x := String sharedPools.` | -             |
| Obtain the names of all shared pools (dictionaries) used by the `String` class (including those inherited from superclasses) | `x := String allSharedPools.` | - |
| Obtain the message selectors (method names) defined for the `String` class | `x := String selectors.` | -               |
| Obtain the source code for the `capitalized` method of the `String` class | `x := String sourceCodeAt: #capitalized.` | -        |
| Obtain a collection of all instances of the `String` class | `x := String allInstances.` | -               |
| Obtain the immediate superclass of the `String` class | `x := String superclass.` | -               |
| Obtain a collection of all superclasses of the `String` class (including the class itself) | `x := String allSuperclasses.` | - |
| Obtain a collection of the receiver class and all its superclasses | `x := String withAllSuperclasses.` | -          |
| Obtain a collection of the immediate subclasses of the `String` class | `x := String subclasses.` | -               |
| Obtain a collection of all subclasses of the `String` class (including those inherited from superclasses) | `x := String allSubclasses.` | - |
| Obtain a collection of the receiver class and all its subclasses | `x := String withAllSubclasses.` | -                |
| Obtain the number of named instance variables for the `String` class | `b := String instSize.` | -                   |
| Check if the `String` class has no indexed instance variables | `b := String isFixed.` | -                      |
| Check if the `String` class has indexed instance variables | `b := String isVariable.` | -                   |
| Check if the indexed instance variables of the `String` class contain objects | `b := String isPointers.` | -               |
| Check if the indexed instance variables of the `String` class contain bytes or words | `b := String isBits.` | -             |
| Check if the indexed instance variables of the `String` class contain bytes | `b := String isBytes.` | -                |
| Check if the indexed instance variables of the `String` class contain words | `b := String isWords.` | -                |
| Get the total number of class entries (i.e. number of classes and metaclasses) | `Object withAllSubclasses size.` | -       |

