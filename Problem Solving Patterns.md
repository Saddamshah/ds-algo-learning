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
> Given two strings, write a function to determine if the second string is an **anagram** of the first. An anagram is a word, phrase, or name formed by rearranging the letters of another, such as _cinema_, formed from _iceman_.

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
