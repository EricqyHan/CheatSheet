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

Array.splice - is a swiss army knife for arrays. It can insert, remove, and replace

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
