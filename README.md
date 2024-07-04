# ALL_INTERVIEWS_QUESTIONS
1. [ Display Original Properties of an Array in JavaScript](#display-original-properties-of-an-array-in-javascript)

---

## Display Original Properties of an Array in JavaScript

### Concept

By using the `prototype`, we can insert new properties in an array, but those will not be considered as original properties. To get original properties, we need to add a check to array elements using the `hasOwnProperty` method.

### Explanation

In JavaScript, arrays can have both **inherited properties** and **own properties**:

- **Inherited Properties**: These are properties inherited from the `Array` prototype, such as methods like `push`, `pop`, `map`, etc.
- **Own Properties**: These are properties directly defined on the array instance itself.

Using the `hasOwnProperty` method, we can filter out the inherited properties and display only the own properties of an array.

### Example

Let's go through an example to illustrate this concept.

#### Step 1: Create an Array

```javascript
let arr = [1, 2, 3];
```

#### Step 2: Add a Custom Property to All Arrays

```javascript
Array.prototype.customProperty = 'I am a custom property';
```

#### Step 3: Iterate Over Properties and Display Only Own Properties

```javascript
function displayOwnProperties(array) {
  for (let key in array) {
    if (array.hasOwnProperty(key)) {
      console.log(`Key: ${key}, Value: ${array[key]}`);
    }
  }
}

// Call the function
displayOwnProperties(arr);
```

#### Full Code Example

```javascript
let arr = [1, 2, 3];

// Adding a custom property to all arrays
Array.prototype.customProperty = 'I am a custom property';

// Function to display only the own properties
function displayOwnProperties(array) {
  for (let key in array) {
    if (array.hasOwnProperty(key)) {
      console.log(`Key: ${key}, Value: ${array[key]}`);
    }
  }
}

// Call the function
displayOwnProperties(arr);
```

#### Output

```
Key: 0, Value: 1
Key: 1, Value: 2
Key: 2, Value: 3
```

The custom property `customProperty` is not included in the output because it is not an own property of `arr`.

### Summary

By using `Array.prototype`, you can add properties or methods to all arrays. However, these properties are inherited and not part of the array's own properties. To display only the original (own) properties of an array, use the `hasOwnProperty` method to filter out inherited properties.

### Further Reading

- [MDN Web Docs: Array.prototype](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype)
- [MDN Web Docs: Object.prototype.hasOwnProperty](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

---
