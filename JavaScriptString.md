# JavaScript String Cheet Sheet

### Converting a number into an array

```js
let myInt = 235345;

// number to string conversion
let temp = "" + myInt;
// turns myInt into string 235345
// forming array with numbers as element
let intArr = [...temp].reduce((acc, n) => acc.concat(+n), []);
// turns temp into [2,3,4,3,4,5]

// Print the result array
console.log(intArr);
// prints [2,3,4,3,4,5]
```

### Turning a number and setting it in descending order

```js
function descendingOrder(n) {
  return parseInt(String(n).split("").sort().reverse().join(""));
}

console.log(descendingOrder(1021));
```
