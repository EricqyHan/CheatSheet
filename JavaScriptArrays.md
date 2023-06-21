# JavaScript Array Cheet Sheet

## Add/Remove Items

- arr.push(...items) – adds items to the end
- arr.pop() – extracts an item from the end
- arr.shift() – extracts an item from the beginning
- arr.unshift(...items) – adds items to the beginning

```js
let arr = ["I", "go", "home"];
delete arr[1];
console.log(arr); // returns ["I", , "home"]
console.log(arr[1]); // returns undefined
console.log(arr.length); // returns 3
```

Here are a few others

### Array.splice - is a swiss army knife for arrays. It can insert, remove, and replace

```js
// Array.splice - is a swiss army knife for arrays. It can insert, remove, and replace

//array.splice(indexToStart, numberOfIndices, "stringToAdd");
const months = ["Jan", "March", "April", "May"];

months.splice(1, 0, "Feb");
console.log(months); // returns ["Jan", "February", "March", "April", "May"]

const months2 = ["Janary", "February", "March", "April", "May"];

// Frm index element, remove number of elements
months2.splice(1, 1);
// From index 1, remove 1 element
console.log(months2);
// returns ["January", "March", "April", "May"]

// Remove x number of elements and replace with x amount
let studyJavaScript = ["I", "study", "JavaScript"];
studyJavaScript.splice(1, 1, "hate");
console.log(studyJavaScript);
// Returns ["I", "hate", "JavaScript"];

//array.splice(indexToStart, numberOfIndices, "stringToAdd");
let studyJavaScript2 = ["I", "study", "JavaScript", "right", "now"];
studyJavaScript2.splice(0, 3, "Let's", "dance");
console.log(studyJavaScript2);
// returns ["Lets", "dance", "right", "now"]

// Here we can see that splice returns the array of removed elements
let studyJavaScript3 = ["I", "study", "React", "right", "now"];
// remove 2 first elements and replate with another
let removed = studyJavaScript3.splice(0, 2);
console.log(removed);
// returns ["I", "study"]

// The splice method is also able to insert the elements without any removal.
// for that we need to set deleteCount to 0
let studyJavaScript4 = ["I", "study", "React", "right", "now"];
// from index 3, delete 0, then insert "and", "JavaScript"
studyJavaScript4.splice(3, 0, "and", "JavaScript");
console.log(studyJavaScript4);
// returns ["I", "study", "React", "and", "Javascript", "right", "now"];

//Negative indexes allowed
let studyJavaScript5 = ["I", "study", "React", "right", "now"];
studyJavaScript5.splice(-3, 0, "JavaScript", "Node", "and");
// from index -3 ("React"), delete 0 elements, then insert "JavaScript", "Node", "and"
console.log(studyJavaScript5);
// returns ["I", "study", "JavaScript", "Node", "and", "React", "right", "now"];
```

### Slice is a much simpler than similar-looking `js arr.splice`. The slice() method slices out a piece of an array into a new array from start to end (end not included).

The syntax is

```js
arr.slice([start], [end]);

let array1 = [5, 3, 1, 9, 7, 4, 2, 8, 6];
let num = array1.slice(1, 4);

// Output: [3, 1, 9]

let arrTest = ["t", "e", "s", "t"];
let arrTestSlice = arrTest.splice(1, 2);
console.log(arrTestSlice);
// returns ["e", "s"]

let arrTestSlice2 = arrTest.slice(-2);
console.log(arrTestSlice2);
// returns ["t", "t"]

let arrTest2 = ["t", "e", "s", "t", "i", "n", "g"];
console.log(arrTest2.slice(-3));
// returns ["i", "n", "g"]
```

### Concat method createa a new array by merging existing arrays

```js
let a = [1, 2];
let b = [3, 4, 5];
let c = a.concat(b);
/// returns [1,2,3,4,5]

let arrConcat = [1, 2];
console.log(arrConcat.concat([3, 4], [5, 6], 7, 8));
// returns [1, 2,3,4,5,6,7,8]

let arrConcat2 = [1, 2];
let arrayLike = {
  0: "something",
  length: 1,
};

console.log(arrConcat2.concat(arrayLike));
// returns [1, 2, {0: 'something', length: 1}]
```

### forEach() method calls a function and iterates over the array items in ascending order without mutating the array.

```js
let names = ["Anna", "John", "Peter"];

// using forEach
names.forEach(function (item, index, arr) {
  arr[index] = "Hello " + item;
});

console.log(names);
// ["Hello Anna", "Hello John", "Hello Peter"]

let lotr = ["Bilbo", "Gandalf", "Nazgul"];
lotr.forEach((item, index, array) => {
  console.log(`${item} is at index ${index} in ${array}`);
});
//returns
// Bilbo is at index 0 in Bilbo,Gandalf,Nazgul
// Gandalf is at index 1 in Bilbo,Gandalf,Nazgul
// Nazgul is at index 2 in Bilbo,Gandalf,Nazgul
```

### Searching in Array with indexOf/lastIndexOf

- arr.indexOf(item, from) – looks for item starting from index from, and returns the index where it was found, otherwise -1.
-
- arr.includes(item, from) – looks for item starting from index from, returns true if found.

```js
const names = ["Anna", "Pete", "Jane", "Luna"];
console.log(names.indexOf("Jane")); // 2
```
