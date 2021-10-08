
# JavaScript Snippets

## Table of Contents
1. [Array](#array)
    * [Remove duplicates](#remove-duplicate)
    * [Deconstruct syntax](#deconstruct-syntax)
2. [Console](#console)
    * [Format JSON output](#json-output)
    * [Console time](#time)
3. [Shorthands](#shorthands)
    * [For loop](#forloop)
    * [And(&&)](#and)
    * [Implicit return](#implicit-return)
    * [Template literals](#template-literals)
4. [Other](#other)
    * [Optional chaining](#optional-chaining)
    * [Default values](#default)
        * [Or operator (||)](#or)
        * [Nullish coalescing operator (??)](#nullish)
        * [Parameters](#parameters)

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

---

## Other <a id="other"></a>

**Optional chaining operator** <a id="optional-chaining"></a>

The optional chaining operator provides a way to simplify accessing values through connected objects when it's possible that a reference or function may be undefined or null.

[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

```javascript
  // Instead of writing:
  let nested = obj.first && obj.first.second;

  // Write:
  let nested = obj.first?.second;
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

**Note: This can cause issues if "age" is set to 0. The output will still be 31. The or operator will compute: (0 || 30 = 30).**

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