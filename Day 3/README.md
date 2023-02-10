
# Day 3

Topic of the Day
- Display only Unique Element in Array (Num - String)
- Remove Dublicate Element from array (Num - String)
- 


## First Method 
```javascript
let data = ['a', 'b', 'c', 'a', 'c', 'b', 'a' ];

function displayUnique(arr) {
  let result = [];
  for (let i = 0; i < arr.length; i++) {
    let isUnique = true;
    for (let j = 0; j < result.length; j++) {
      if (arr[i] === result[j]) {
        isUnique = false;
        break;
      }
    }
    if (isUnique) {
      result.push(arr[i]);
    }
  }
  return result;
}
console.log(displayUnique(['a', 'b', 'c', 'a', 'c', 'b', 'a' ]))
```

## Second Method 
In this implementation, an object **`result`** is used to store unique values as properties. The properties are assigned a value of **`true`** to indicate that they are present in the input array. The  **`Object.keys`** method is then used to extract the property names from the **`result`** object and return them as an array. This array contains only the unique values from the input array.
```javascript
function displayUnique(arr) {
  let result = {};
  for (let i = 0; i < arr.length; i++) {
    result[arr[i]] = true;
  }
  return Object.keys(result);
}
```
Details:

The line **`result[arr[i]] = true;`** sets a property in the **`result`** object with the key **`arr[i]`** and the value true.

In this implementation, an object result is used to store unique values. Each time the code encounters a unique value in the input array arr, it sets a property in the result object with the same value as the key, and sets its value to true. This way, when the same value appears again in the array, the code does not add it to the result object again because it already exists as a property in the object.

At the end, the Object.keys method is used to extract the property names from the result object, which are the unique values from the input array, and return them as an array.


## Remove Duplicate Values from a JavaScript Array
You can use the **indexOf()** method in conjugation with the push() remove the duplicate values from an array or get all unique values from an array in JavaScript.

```javascript
// Defining function to get unique values from an array
    function getUnique(array){
        var uniqueArray = [];
        
        // Loop through array values
        for(i=0; i < array.length; i++){
            if(uniqueArray.indexOf(array[i]) === -1) {
                uniqueArray.push(array[i]);
            }
        }
        return uniqueArray;
    }
    
    var names = ["John", "Peter", "Clark", "Harry", "John", "Alice"];
    var uniqueNames = getUnique(names);
    console.log(uniqueNames); // Prints: ["John", "Peter", "Clark", "Harry", "Alice"]
```

Alternatively, you can use the newly introduced ES6 **for-of** loop instead of for loop to perform this filtration very easily, as demonstrated in the following example:
```javascript
 // Defining function to get unique values from an array
    function getUnique(array){
        var uniqueArray = [];
        
        // Loop through array values
        for(var value of array){
            if(uniqueArray.indexOf(value) === -1){
                uniqueArray.push(value);
            }
        }
        return uniqueArray;
    }
    
    var names = ["John", "Peter", "Clark", "Harry", "John", "Alice"];
    var uniqueNames = getUnique(names);
    console.log(uniqueNames); // Prints: ["John", "Peter", "Clark", "Harry", "Alice"]
```

### ![GG](https://media.geeksforgeeks.org/gfg-gg-logo.svg) How to remove duplicate elements from JavaScript Array ? 

[Detail Link Here](https://www.geeksforgeeks.org/how-to-remove-duplicate-elements-from-javascript-array/)


#### Javascript filter() Method: 

```javascript
 var arr = ["apple", "mango", "apple", 
            "orange", "mango", "mango"];
      
    function removeDuplicates(arr) {
        return arr.filter((item, 
            index) => arr.indexOf(item) === index);
    }
      
    console.log(removeDuplicates(arr));  // ["apple", "mango", "orange"]
```

#### Javascript set() Method:
```javascript
var arr = ["apple", "mango", "apple",
            "orange", "mango", "mango"];
      
    function removeDuplicates(arr) {
        return [...new Set(arr)];
    }
      
    console.log(removeDuplicates(arr)); // ["apple", "mango", "orange"]
```
For More Methods Visit ![GG](https://media.geeksforgeeks.org/gfg-gg-logo.svg)
[Detail Link Here](https://www.geeksforgeeks.org/how-to-remove-duplicate-elements-from-javascript-array/)
