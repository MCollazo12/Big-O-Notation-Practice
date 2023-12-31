## Big-O Notation Practice

### Step One: Simplifying Expressions
Simplify the following big O expressions as much as possible:

1) O(n+10) --> O(n) --> Ignore constant of 10
2) O(100*n) --> O(n) --> Ignore constant of 100
3) O(25) --> O(1) --> Input sized fixed regardless of value
4) O(n^2 + n^3) --> O(n^3) --> n^3 is the dominant term
5) O(n + n + n + n) --> O(n) --> Arithmetic operations are constant
6) O(1000 * log(n) + n) --> O(n) --> Linear growth (n) dominates log growth
7) O(1000 * n * log(n)) --> O(n * log(n)) --> Ignore constant 
8) O(2^n + n^2) --> O(2^n) --> The exponential term grows faster than the quadratic
9) O(5+3+1) --> O(1) --> All constants, so input size is fixed regardless of value
10) O(n + n^(1/2) + n^2 + n * log(n)^10) --> O(n^2) --> Quadratic grows faster than all other terms

### Step Two: Calculating Time Complexity
Determine the time complexities for each of the following functions:
```js
function logUpTo(n) {
  for (let i = 1; i <= n; i++) {
    console.log(i);
  }
}
```
O(n) time complexity is linear with respect to n

```js
function logAtLeast10(n) {
  for (let i = 1; i <= Math.max(n, 10); i++) {
    console.log(i);
  }
}
```
O(n) time complexity still varies based on the input n

```js
function logAtMost10(n) {
  for (let i = 1; i <= Math.min(n, 10); i++) {
    console.log(i);
  }
}
```
O(1) because the loop is constrained to a max of 10 which is a constant

```js
function onlyElementsAtEvenIndex(array) {
  let newArray = [];
  for (let i = 0; i < array.length; i++) {
    if (i % 2 === 0) {
      newArray.push(array[i]);
    }
  }
  return newArray;
}
```
O(n) number of operations in loop grows linearly with input array

```js
function subtotals(array) {
  let subtotalArray = [];
  for (let i = 0; i < array.length; i++) {
    let subtotal = 0;
    for (let j = 0; j <= i; j++) {
      subtotal += array[j];
    }
    subtotalArray.push(subtotal);
  }
  return subtotalArray;
}
```
O(n^2) outer loop runs n times, inner loop runs from 0 up to i. Inner loop will run n times in worst case, so (n*n)

```js
function vowelCount(str) {
  let vowelCount = {};
  const vowels = "aeiouAEIOU";

  for (let char of str) {
    if(vowels.includes(char)) {
      if(char in vowelCount) {
        vowelCount[char] += 1;
      } else {
        vowelCount[char] = 1;
      }
    }
  }

  return vowelCount;
}
```
O(n) because we're iterating through each char in the input str once (and the arithmetic operations are constant)

### Part 3 - Short Answer
Anser the following questions:

1. True or false: n^2 + n is O(n^2) --> True
2. True or false: n^2 * n is O(n^3) --> True
3. True or false: n^2 + n is O(n) --> False
4. What’s the time complexity of the .indexOf array method? --> O(n)
5. What’s the time complexity of the .includes array method? --> O(n)
6. What’s the time complexity of the .forEach array method? --> O(n)
7. What’s the time complexity of the .sort array method? --> O(n * log(n)) because the input array is being divided
8. What’s the time complexity of the .unshift array method? --> O(n) because the number of shifts grows linearly
9. What’s the time complexity of the .push array method? --> O(1)
10. What’s the time complexity of the .splice array method? --> O(n) because number of shifts increases with input
11. What’s the time complexity of the .pop array method? --> O(1)
12. What’s the time complexity of the Object.keys() function? -> O(n), based on the number of keys in the object





























