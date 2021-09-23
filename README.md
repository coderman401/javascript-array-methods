# Top 20 JavaScript array methods every JS beginner should know!

Quick array method recap:

Array methods are built -in functions in JavaScript that you apply to arrays.Each method has a particular function that changes or manipulates the array.

It saves us time because we can use methods instead of hard coding everything!!😅

#


### 1) pop()

- Removes the LAST element of an array and returns that removed element. This method changes the original array and its length

```
const fruits = ['Apple', 'Banana', 'Mango', 'Orange'];

let fruitsPop = fruits.pop();

console.log(fruits); // ['Apple', 'Banana', 'Mango'];

console.log(fruitsPop); // 'orange'
```
#

### 2) push()

- The opposite of pop(), push() adds one or more elements to the back of an array.This method changes the original array, and returns the length of the changed array.

```
const fruits = ['Apple', 'Banana', 'Mango', 'Orange'];

let fruitsPop = fruits.push('Pineapple', 'Watermelon');

console.log(fruits); // ['Apple', 'Banana', 'Mango', 'Orange', 'Pineapple', 'Watermelon']

console.log(fruitsPop); // 6
```
#

### 3) shift()

- shift() removes the FIRST element of an array, and returns the removed element.This method also changes the original array and its length.

```
const fruits = ['Apple', 'Banana', 'Mango', 'Orange'];

let fruitsPop = fruits.shift();

console.log(fruits); // ['Banana', 'Mango', 'Orange']

console.log(fruitsPop); // 'Apple'
```
#

### 4) unshift()

- unshift() is the opposite of shift()! unshift() adds one or more elements to the start of an array, and returns the new length of the array.
- Order matters; the elements will show up in the order in which you pass them in unshift().

```
const fruits = ['Apple', 'Banana', 'Mango', 'Orange'];

let fruitsPop = fruits.unshift('Pineapple');

console.log(fruits); // [ Pineapple', 'Apple', 'Banana', 'Mango', 'Orange']

console.log(fruitsPop); // 5
```
#

### 5) slice()

- slice() selects a chunk of an array & returns a NEW array with a copy of all elements selected from the start index to the end index.The original array does NOT change.
- The element with the ending index isn't included.

```
const fruits = ['Apple', 'Banana', 'Mango', 'Orange', 'Pineapple', 'Watermelon'];

console.log(fruits.slice(0, 3));
// ['Apple', 'Banana', 'Mango'] (end index 3 not included)

console.log(fruits.slice(1, 2));
// [Banana'] (end index 2 'Mango' no included)

console.log(fruits.slice(3));
// ['Orange', 'Pineapple', 'Watermelon']
// when end index not applied, it takes all elements after the start index
```
#

### 6) splice()

- splice() DOES change the original array.It removes, replaces, or adds new elements to the array.
- splice() method returns an array of the deleted elements.If 0 elements are removed, it returns an empty array.

```
let fruits = ['Apple', 'Banana', 'Mango', 'Orange', 'Pineapple'];

// start index 1 and end index 4, remove elements starting at index 1 and ending at index 4
console.log(fruits.splice(1, 4));
// returns removed elements ['Banana', 'Mango', 'Orange', 'Pineapple']
console.log(fruits);
// original array is changed, array returns ['Apple']

// start index 1 and end index 0, adds the word 'Cherry' at index 1
console.log(fruits.splice(1, 0, 'Cherry'));
//  0 elements removed, so returns an empty array
console.log(fruits);
// 'Cherry' is at index 1 ['Apple', 'Cherry', 'Banana', 'Mango', 'Orange', 'Pineapple']

// start index 2 and end index 1, deletes one word starting  at index 2 , and replaces it with string 'Watermelon'
console.log(fruits.splice(2, 1, 'Watermelon'));
// returns replaced word ['Mango']
console.log(fruits);
// ['Apple', 'Banana', 'Watermelon', 'Orange', 'Pineapple']
```
#

### 7) join()

- join() returns a NEW STRING of array elements either separated by commas or a specified separator.
- If there’s only one element in the array, that element is returned as a string with no separator.

```
const introduction = ['Hello', 'I', 'am', 'developer'];

console.log(introduction.join());
// 'Hello,I,am,developer'

console.log(introduction.join(', '));
// 'Hello, I, am, developer'

console.log(introduction.join(' '));
// 'Hello I am developer'

console.log(introduction.join(' . '));
// 'Hello . I . am . developer'
```
#

### 8) toString()

- toString() converts an array into a string.

```
const introduction = ['Hello', 'I', 'am', 'developer'];

console.log(introduction.toString());
// 'Hello,I,am,developer'
```
#

### 9) forEach()

- forEach() helps you loop through the elements of an array.For every array element, it executes a callback function.

```
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

nums.forEach(num => console.log(num));
// in the `nums` array, for each element (num), log (num)
```
#

### 10) map()

- map() creates a NEW array with the return value of the callback function called on each element in the array.

```
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

let numMap = nums.map(num => {
    return num - 2
});
// for every element (num) in 'nums` array, multiply it by 2

console.log(numMap); // [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```
#

### 11) filter()

- filter() returns a NEW array that 'filters' out elements from an array.
- Each element of the array is passed to a callback function that either returns `true` or`false`.If the callback returns `true` for a specific element, that element is added to the new array.

```
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

let filteredNum = nums.filter(num => {
    return num % 2 === 0
});
// here we are filtering out even numbers
//  if `num % 2 === 0` is true for an element , add that element to the new filtered array

console.log(filteredNum); // [2, 4, 6, 8, 10]
```
#

### 12) find()

- find() returns a first element in the array that satisfies the callback function. If no elements pass the test provided by the callback function, find() returns`undefined`.

```
const array = [
    { id: 1, name: 'name1' },
    { id: 2, name: 'name2' },
    { id: 3, name: 'name3' },
];

let object = array.find((element) => {
    return element.id === 2;
})

console.log(object); // { id: 2, name: 'name2' }
```
#

### 13) findIndex()

- findIndex() returns the index of the first element in the array that satisfies the callback function. If no elements pass the test provided by the callback function, findIndex() returns - 1.

```
const array = [
    { id: 1, name: 'name1' },
    { id: 2, name: 'name2' },
    { id: 3, name: 'name3' },
];

let object = array.findIndex((element) => {
    return element.id === 2;
})

console.log(object); // 1
// return the index of the satisfied condition
```
#

### 14) includes()

- includes() checks if the array includes the item passed to the method.It returns either `true` or`false`.

```
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

let isNumIncludes = nums.includes(2);

console.log(isNumIncludes); // true
```
#

### 15) concat()

- concat() merges two or more arrays into a NEW array.

```
const frontend = ['html', 'css', 'javascript'];
const backend = ['php', 'python', 'java'];

let all = frontend.concat(backend);

console.log(all);
// ['html', 'css', 'javascript', 'php', 'python', 'java']

console.log(frontend);
// `frontend` remains unchanged ['html', 'css', 'javascript']

console.log(backend);
// `backend` remains unchanged ['php', 'python', 'java']
```
#

### 16) sort()

- sort() sorts the elements of an array in ascending order.This means is that it first converts the elements into strings, then compares its code(UTF - 16).It changes the original array, and returns the sorted array.

```
const days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'];

const sortAsc = days.sort(); // OR days.sort((a, b) => (a < b ? -1 : 1));
console.log(sortAsc);
// sort `days` in ascending order ['Friday', 'Monday', 'Thursday', 'Tuesday', 'Wednesday']

const sortDesc = days.sort((a, b) => (a > b ? -1 : 1));
console.log(sortDesc);
// sort `days` in descending order ['Wednesday', 'Tuesday', 'Thursday', 'Monday', 'Friday']


const nums = [5, 3, 2, 4, 9, 10, 7, 1, 6, 8];

let sortAsc = nums.sort();
console.log(sortAsc);
// sort the number as string [1, 10, 2, 3, 4, 5, 6, 7, 8, 9]

let sortAscNum = nums.sort((a, b) => a - b);
console.log(sortAscNum);
// sort `nums` in ascending order [1, 2, 3, 4,  5, 6, 7, 8, 9, 10]

const sortDesc = nums.sort((a, b) => b - a);
console.log(sortDesc);
// sort `nums` in descending order [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```
#

### 17) reverse()

- reverse() reverses an array; the first element becomes last, and the last becomes first. It changes the original array, and it returns the reversed array.

```
const colors = ['Red', 'Green', 'Blue', 'Black', 'White'];

let reversed = colors.reverse();

console.log(reversed);
// ['White', 'Black', 'Blue', 'Green', 'Red']

//reversing the string using the reverse function
const string = 'Hello world';
// will split the string by split()` method and make array of it then reverse the array using `reverse()` method
and then again join the array using `join()` method

let reversedString = string.split('').reverse().join('');

console.log(reversedString);
// 'dlrow olleH'
```
#

### 18) every()

- every() tests if every element in an array passes the test implemented by the callback function. It returns a boolean value.
- If all elements in the array return `true` when passed the function, every() returns `true`.

```
const teenager = [13, 14, 15, 16, 17];
const adult = [18, 19, 20, 21, 22];

//element in the `teenager` array won't pass the test
let isAdult = teenager.every(age => {
    return age >= 18;
});
console.log(isAdult); //false

isAdult = adult.every(age => {
    return age >= 18;
});
console.log(isAdult); // true
```
#

### 19) some()

- Similar to every(), some() returns `true` if ANY(some) element in the array passes the test implemented by the callback function.
- Every element isn't required to pass the callback; if one element returns `true`, some() method returns `true`

```
const greaterThanFive = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const noneGreaterThanFive = [1, 2, 3, 4, 5];

// test weather element is greater than 5
let some = greaterThanFive.some(num => num > 5);
let none = noneGreaterThanFive.some(num => num > 5);

console.log(some);
//  returns `true` because 6, 7, 8, 9 are greater than 5
console.log(none);
// returns `false` because no element is greater than 5
```
#

### 20) reduce()

- reduce() reduces the array into a single element. It passes the return value of the previous element in the callback function
- To put it simply, it kind of adds the result of the previous value to the current value.

```
// summing an array

// `accumulator` holds the total sum, and `currentValue` represents each element
let reduceNums = [1, 2, 3, 4, 5, 6].reduce((accumulator, currentValue) => {
    return accumulator + currentValue; // this returned value will be used for the next iteration's `accumulator`
});
// first iteration: `accumulator` is 1, `currentValue` is 2
// 1 + 2 = 3, number 3 is returned
// 3 is the `accumulator` for second iteration

// second iteration: `accumulator`` is 3, `currentValue` is 3
// 3 + 3 = 6, number 6 is returned
// 6 is the `accumulator` for third iteration

// third iteration: `accumulator`` is 6, `currentValue` is 4
// 6 + 4 = 10, number 10 is returned
// 10 is the `accumulator` for fourth iteration

console.log(reduceNums); // 21
```
#

- extended from [Twitter Thread](https://twitter.com/codingyuri/status/1438873876398755844)