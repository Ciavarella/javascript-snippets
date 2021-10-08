
# JavaScript Snippets

## Table of Contents
1. [Array](#Array)
2. [Console](##Console)

<details>
  <summary>Array</summary>

  Remove duplicates from an Array

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

  ```javascript
    const arr = [1, 2, 3, 3, 3, 6, 7, 8, 8, 9]
    const filtered = [...new Set(arr)]
    console.log(filtered)
    // Output: [1, 2, 3, 6, 7, 8, 9] 
  ```

  &nbsp;

  Deconstruct assignment syntax

  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

  ```javascript
    const things = ['House', 'Computer', 'CoolCat']
    const { 1: hobby } = things
    console.log(hobby)
    // Output: "Computer"
  ```
</details>

---
 # some more text
 ```
 dlaksjdas
 df
 dgäkdfö
 glksd
 fölgkdöf
 lgks
 dölfkgö
 sdlfkgös
 dlfkg
 södflgödslfkgsödlfkgösdlfkg
 sdöflkjsdf
 jsldkfjsd
 fjlskdjf
 sdlfkjsdf
 lsdfjlksdjf
 llSKDJflksdf
 ```
---
# dajlksdhkjas
```
alskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjd
alskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjdalskjdas
jlaskdjas
jlkasd
jlasökd
jlkasdjlk
asjldajsd
laskdjlkajsd
jklaskjdlkasd
jlasjdlkas
jlaskdjlkasd
jlkasdjlkjasd
lkasjdlkjasd
lkasjdlkajsd
lkasjdlkasjd
jlaskjd
```


&nbsp;

## Console

Format JSON string output

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

<details>
  <summary>Click to expand</summary>
  Hello

  ```javascript
    console.log('Expand snippet') 
  ``` 
</details>
