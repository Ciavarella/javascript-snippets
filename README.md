
# JavaScript Snippets

## Table of Contents
1. [Array](#array)
    1. [Remove duplicates](#remove-duplicate)
    2. [Deconstruct syntax](#deconstruct-syntax)
2. [Console](#console)
    1. [Format JSON output](#json-output)

---

## Array <a id="array"></a>

  Remove duplicates from an Array <a id="remove-duplicate"></a>

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

  ```javascript
    const arr = [1, 2, 3, 3, 3, 6, 7, 8, 8, 9]
    const filtered = [...new Set(arr)]
    console.log(filtered)
    // Output: [1, 2, 3, 6, 7, 8, 9] 
  ```

  &nbsp;

  Deconstruct assignment syntax <a id="deconstruct-syntax"> 

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

  ```javascript
    const things = ['House', 'Computer', 'CoolCat']
    const { 1: hobby } = things
    console.log(hobby)
    // Output: "Computer"
  ```

---

## Console <a id="console"></a>

Format JSON string output <a id="json-output"></a>

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
