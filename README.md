
# JavaScript Snippets

## Table of Contents
1. [Array](#array)
    * [Remove duplicates](#remove-duplicate)
    * [Deconstruct syntax](#deconstruct-syntax)
    * [Array contains value](#array-contains-value)
        * [String](#contains-string)
        * [Number](#contains-number)
    * [Array Flat](#array-flat)
    * [Get frequency](#frequency)
    * [Generate range of numbers](#generate)
    * [Merging Arrays](#merging)
2. [Console](#console)
    * [Format JSON output](#json-output)
    * [Console time](#time)
3. [Shorthands](#shorthands)
    * [For loop](#forloop)
    * [And(&&)](#and)
    * [Implicit return](#implicit-return)
    * [Template literals](#template-literals)
    * [If else](#if-else)
    * [Converting string into number](#convert)
4. [Other](#other)
    * [Optional chaining](#optional-chaining)
    * [Default values](#default)
        * [Or operator (||)](#or)
        * [Nullish coalescing operator (??)](#nullish)
        * [Parameters](#parameters)
    * [Capitalize string](#capitalize)

---

## Array <a id="array"></a>

  **Remove duplicates from an Array** <a id="remove-duplicate"></a>

  Set objects are collections of values. You can iterate through the elements of a set in insertion order. A value in the Set may only occur once; it is unique in the Set's collection.

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

  ```javascript
    const arr = [1, 2, 3, 3, 3, 6, 7, 8, 8, 9]
    const filtered = [...new Set(arr)]
    console.log(filtered)
    // Output: [1, 2, 3, 6, 7, 8, 9]

    /*
      Note: This can be an issue with TypeScript.
      If you get the error: "Type 'Set' is not an array type."
      You can change your tsconfig "target": "ES6" (or higher)
      Or you can use this syntax:
    */
    const filtered = Array.from(new Set(arr))
  ```

  &nbsp;

  **Deconstruct assignment syntax** <a id="deconstruct-syntax"></a>

  The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

  ```javascript
    const things = ['House', 'Computer', 'CoolCat']
    const { 1: hobby } = things
    console.log(hobby)
    // Output: "Computer"
  ```

  &nbsp;

  **Check if array contains value** <a id="array-contains-value"></a>

  **String** <a id="contains-string"></a> 

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)

  ```javascript
    const array = ['Audi', 'BMW', 'Volvo']
    console.log(array.includes('Audi'))
    // Output: true

    // Note: This is case sensitive.
    console.log(array.includes('audi'))
    // Output: false

    const result = array.map(e => e.toLocaleLowerCase()).includes('bmw')
    console.log(result)
    // Output: true
  ```

  **Number** <a id="contains-number"></a>

  ```javascript
    const arr = [1, 2, 3, 4, 5]

    console.log(arr.includes(3))
    // Output: true

    console.log(arr.includes('3'))
    // Output: false
  ```

  &nbsp;

  **Flatten array** <a id="array-flat"></a>

  The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)

  ```javascript
    const array = [1, [2, 3], 4]
    console.log(array.flat())
    // Output: [1, 2, 3, 4]

    const arr = [1, [2,[3, 4], 5]]
    console.log(arr.flat(1))
    // Output: [1, 2, [3, 4], 5]

    console.log(arr.flat(2))
    // Output: [1, 2, 3, 4, 5]

    // Infinity is also possible as a parameter.
    console.log(arr.flat(Infinity))
  ```

  &nbsp;

  **Get frequency** <a id="frequency"></a>

  ```javascript
    const getFrequencyCounts = (strings) => strings.reduce(
      (counts, string) => {
        counts[string] ??= 0
        counts[string]++
        return counts
      }, {})

    const arr = ['hello', '1337', 'world', 'hello', 'hello', '1337']
    const frequency = getFrequencyCounts(arr)
    console.log(frequency)
    // Output: {1337: 2, hello: 3, world: 1}
  ```

  &nbsp;

  **Generate range of numbers** <a id="generate"></a>

  ```javascript
    const generateRange = (start, end) => Array.from(Array(end)).map((_,i) => i+start)
    const generatedArr = generateRange(5,10);
    console.log(generatedArr);
    // Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

    // If you don't need to set a start and just want to set the amount:
    const generate = amount => [...Array(amount).keys()]
    const arr = generate(5)
    console.log(arr)
    // Output: [0, 1, 2, 3, 4]
  ```

  &nbsp;

  **Merging Arrays** <a id="merging"></a>

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

  Without spread syntax, to create a new array using an existing array as one part of it, the array literal syntax is no longer sufficient and imperative code must be used instead using a combination of push(), splice(), concat(), etc. With spread syntax this becomes much more succinct.

  ```javascript
    const numArr = [1, 2, 3]
    const moreNums = [4, 5, 6]

    const merged = [...numArr, ...moreNums]
    console.log(merged)
    // Output: [1, 2, 3, 4, 5, 6]
  ```

---

## Console <a id="console"></a>

**Format JSON string output** <a id="json-output"></a>

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)

```javascript
  const user = {
    firstName: 'John',
    lastName: 'Doe',
    age: '30',
    city: 'Stockholm'
  }

  const stringify = JSON.stringify(user)
  console.log(stringify)
  // Output: "{'firstName':'John','lastName':'Doe','age':'30','city':'Stockholm'}"

  const formated = JSON.stringify(user, null, 2)
  console.log(formated)
  /*
  Output: 
  "{
    'firstName': 'John',
    'lastName': 'Doe',
    'age': '30',
    'city': 'Stockholm'
  }"
  */
```

&nbsp;

**time() & timeEnd()** <a id="time"></a>

[MDN Documentation time](https://developer.mozilla.org/en-US/docs/Web/API/console/time)

The console.time() method starts a timer you can use to track how long an operation takes.

[MDN Documentation timeEnd](https://developer.mozilla.org/en-US/docs/Web/API/console/timeEnd)

The console.timeEnd() stops a timer that was previously started by calling console.time().

```javascript
  console.time("timer");

  // Do something here

  console.timeEnd("timer");
  // Output: timer: 0.2177734375 ms

```

---

## ShortHands <a id="shorthands"></a>

**For loop** <a id="forloop"></a>

```javascript
  const arr = ['blue', 'red', 'orange', 'yellow', 'cyan']
  for (let color of arr) console.log(color)
  /* Output:
    "blue"
    "red"
    "orange"
    "yellow"
    "cyan"
  */
```

&nbsp;

**And** <a id="and"></a>

Avoid if statements with the and operator.

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)

```javascript
  // Avoid:
  if(foo) {
    bar()
  }

  // Do:
  foo && bar()
```

&nbsp;

**Implicit return** <a id="implicit-return"></a>

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

```javascript
  const add = (x, y) => x + y

  // Instead of:
  const add = (x, y) => {
    return x + y
  }
```

&nbsp;

**Template literals** <a id="template-literals"></a>

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

```javascript
  const firstName = 'John'
  const lastName = 'Doe'

  // Instead of writing:
  const greeting = "Hello" + " " + firstName + " "  + lastName

  // Write:
  const greeting = `Hello ${firstName} ${lastName}`
```

&nbsp;

**If else** <a id="if-else"></a>

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

The conditional (ternary) operator is frequently used as a shortcut for the if statement.

```javascript
  // Syntax
  condition ? expressionIfTrue : expressionIfFalse

  const greet = name => name ? `Hello ${name}` : 'Hello stranger'

  greet()
  // Output: 'Hello stranger'

  greet('John')
  // Output: 'Hello John'
```

&nbsp;

**Coverting string into number** <a id="convert"></a>

```javascript
  const leet = "1337"
  const decimal = "13.37"

  const num = parseInt(leet)
  // Output: 1337
  const num2 = parseFloat(decimal)
  // Output: 13.37

  // Shorthand:
  const num = +leet
  const num2 = +decimal
```

---

## Other <a id="other"></a>

**Optional chaining operator** <a id="optional-chaining"></a>

The optional chaining operator provides a way to simplify accessing values through connected objects when it's possible that a reference or function may be undefined or null.

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

```javascript
  // Instead of writing:
  let nested = obj.first && obj.first.second

  // Write:
  let nested = obj.first?.second
```

&nbsp;

**Default values** <a id="default"></a>

Set default values if no values are provided. <a id="or"></a>

```javascript
  const user = {
    name: 'John'
  }

  // Use the OR operator to set "age"
  const age = user.age || 30

  console.log(age)
  // Output: 30

```

**Note: This can cause issues if "age" is set to 0. The output will still be 30. The or operator will compute: (0 || 30 = 30).**

**Replace the OR operator (||) with Nullish coalescing operator (??).** <a id="nullish"></a>

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)

```javascript
  const user = {
    name: 'John',
    age: 0
  }

  // Using nullish coalescing operator.
  const age = user.age ?? 30

  console.log(age)
  // Output: 0

```

**Default parameters (function)** <a id="parameters"></a>

Default function parameters allow named parameters to be initialized with default values if no value or undefined is passed.

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

```javascript

  // Set the default value
  const func = (arg = 'default') => {
    console.log(arg)
  }

  func('Hello')
  // Output: 'Hello'
  func()
  // Output: 'default'
```

&nbsp;

**Capitalize string** <a id="capitalize"></a>

Return string with the first letter capitalized.

```javascript
  const capitalize = str => `${str.charAt(0).toUpperCase()}${str.slice(1)}`

  capitalize('hello')
  // Output: 'Hello'
```

  This is also possible with CSS.

```css
  text-transform: capitalize;

  /*
    Note: With CSS sentences will look like this:
    Input: "hello world, here i am"
    Output: "Hello World, Here I Am"
  */


  /* To achive the just the first letter you can do the following: */

  .someClass:fist-letter {
    text-transform: capitalize; 
  }
  /*  Input: "hello world, here i am" */
  /*  Output: "Hello world, here i am" */

```