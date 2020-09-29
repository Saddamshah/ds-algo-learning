## Problem Solving Patterns

**A) Frequency Counter Pattern**   
    &nbsp;  This pattern **uses objects** or sets to collect values / frequencies of values     
    &nbsp;  This can often avoid the need for **nested loops** or `O(N^2)` operations with arrays / strings
    
## Example
>Write a function called **same**, which accepts two arrays. The function should return **true** if every value in the array has it's **corresponding value squared** in the second array. The **frequency of values must be the same.**

```javascript
same([1,2,3], [4,1,9]) // true
same([1,2,3], [1,9])   // false
same([1,2,1], [4,4,1]) // false (must be same frequency)
```
### A NAIVE SOLUTION
```javascript
function same(arr1, arr2){
    if(arr1.length !== arr2.length) return false;
   
    for(let i = 0; i < arr1.length; i++){
        let correctIndex = arr2.indexOf(arr1[i] ** 2)
        if(correctIndex === -1) {
            return false;
        }
        arr2.splice(correctIndex,1)
    }
    return true
}

Time Complexity - O(N^2)
```
### REFACTORED
```javascript
function same(arr1, arr2){
    if(arr1.length !== arr2.length) return false;
    
    let frequencyCounter1 = {}
    let frequencyCounter2 = {}
    
    for(let val of arr1){
        frequencyCounter1[val] = (frequencyCounter1[val] || 0) + 1
    }
    
    for(let val of arr2){
        frequencyCounter2[val] = (frequencyCounter2[val] || 0) + 1        
    }
    
    for(let key in frequencyCounter1){
        if(!(key ** 2 in frequencyCounter2)){
            return false
        }
        if(frequencyCounter2[key ** 2] !== frequencyCounter1[key]){
            return false
        }
    }
    
    return true
}

Time Complexity - O(n)
```
### Exercise No 1
> Given two strings, write a function to determine if the second string is an **anagram** of the first. An anagram is a word, phrase, or name formed by rearranging the letters of another, **such as _cinema_, formed from _iceman_**.

```javascript
validAnagram('', '')                 // true 
validAnagram('aaz', 'zza')           // false 
validAnagram('anagram', 'nagaram')   // true 
validAnagram("rat","car")            // false 
validAnagram('awesome', 'awesom')    // false 
validAnagram('qwerty', 'qeywrt')     // true 
validAnagram('texttwisttime', 'timetwisttext')  // true
```

### Exercise No 2
> Write a function called **sameFrequency**. Given two integers, find out if the two numbers have the **same frequency of digits**. Your solution MUST have **Time: O(N)**

```javascript
sameFrequency(182.281)           //true
sameFrequency(34, 14)            //false
sameFrequency(3589578, 5879385)  //true
sameFrequency(22, 222)           //false
```

### Exercise No 3
> Implement a function called, **areThereDuplicates** which accepts a variable number of arguments, and checks whether there are any duplicates among the arguments passed in. **Time - O(N) Space - O(N)**

```javascript
areThereDuplicates(1, 2, 3)  //false  
areThereDuplicates(1, 2, 2)  //true  
areThereDuplicates('a', 'b', 'c', 'a')  //true  
```
### Exercise No 4
> Given an **array of integers nums** and an **integer target**, return indices of the two numbers such that they add up to target and you may not use the same element twice.You can return the answer in any order.

```javascript
twoSum([2, 7, 11, 15], 9)  // [0, 1]
twoSum([3, 2, 4], 6)       // [1, 2]
twoSum([3,3], 6)           // [0, 1]
```

**A) Multiple Pointers Pattern**   
    &nbsp;  Creating pointers or values that correspond to an index or position and move towards the beginning, end or middle based on a certain condition.     
    &nbsp;  Very efficient for solving problems with minimal Space as well.
    
## Example
> Write a function called sumZero which accepts a sorted array of integers. The function should find the first pair where the sum is 0. Return an array that includes both values that sum to zero or undefined if a pair does not exist.
    
```javascript
sumZero([-3, -2, -1, 0, 1, 2, 3]); // [-3, 3]
sumZero([-2, 0, 1, 3]); // undefined
sumZero([1, 2, 3]); // undefined
``` 
### A NAIVE SOLUTION
```javascript
const sumZero = arr => {
  for (let i = 0; i < arr.length; i++)
    for (let j = i + 1; j < arr.length; j++)
      if (arr[i] + arr[j] === 0)
        return [arr[i], arr[j]];
};

Time Complexity - O(N^2) | Space Complexity O(1)
```
### REFACTORED
```javascript
const sumZero = arr => {
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    let sum = arr[left] + arr[right];

    if (sum === 0) return [arr[left], arr[right]];
    else if (sum < 0) left++;
    else right--;
  }
};

Time Complexity - O(N) | Space Complexity O(1)
```
### Exercise No 1
> Implement a function called **countUniqueValues**, which accepts a sorted array, and counts the unique values in the array. There can be negative numbers in the array, but it will always be sorted.

```javascript 
countUniqueValues([1, 1, 1, 1, 1, 2]); // 2
countUniqueValues([-2, -1, -1, 0, 1]); // 4
countUniqueValues([]); // 0
```

### Exercise No 2
> Write a function called averagePair. Given a sorted array of integers and a target average, determine if there is a pair of values in the array where the average of the pair equals the target average. There may be more than one pair that matches the average target.

```javascript
averagePair([1, 2, 3], 2.5); // true
averagePair([1, 3, 3, 5, 6, 7, 10, 12, 19], 8); // true
averagePair([-1, 0, 3, 4, 5, 6], 4.1); // false
averagePair([], 4); // false
```
### Exercise No 3
> Write a function called isSubsequence which takes in two strings and checks whether the characters in the first string form a subsequence of the characters in the second string. In other words, the function should check whether the characters in the first string appear somewhere in the second string, without their order changing.

```javascript
isSubsequence('hello', 'hello world'); // true
isSubsequence('sing', 'sting'); // true
isSubsequence('abc', 'acb'); // false (order matters)
```
