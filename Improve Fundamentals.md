# Let's Improve Your Fundamentals.
> **_Practice Is The Only Way To Improve_**


### Exercise No 1 
> **Extract the domain name from a URL**   
> Write a function that when given a URL as a string, parses out just the domain name and returns it as a string.

```javascript
domainName("https://www.cnet.com")                 // "cnet"
domainName("http://google.co.jp")                  // "google"
domainName("www.xakep.ru")                         // "xakep"
domainName("https://youtube.com")                  // "youtube"
domainName("http://github.com/carbonfive/raygun")  // "github" 
domainName("http://www.zombie-bites.com")          // "zombie-bites"
```

### Exercise No 2  
> **Create Phone Number**    
> Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

```javascript
createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0])  // "(123) 456-7890"
createPhoneNumber([1, 1, 1, 1, 1, 1, 1, 1, 1, 1])  // "(111) 111-1111"
createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0])  // "(123) 456-7890"
```

### Exercise No 3  
> **Moving Zeros To The End**    
> Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

```javascript
moveZeros([false,1,0,1,2,0,1,3,"a"]) // [false,1,1,2,1,3,"a",0,0]
moveZeros([1,2,0,1,0,1,0,3,0,1])     // [ 1, 2, 1, 1, 3, 1, 0, 0, 0, 0 ]
```

### Exercise No 4
> **Array.diff**    
> Your goal in this problem is to implement a difference function, which subtracts one list from another and returns the result.
It should remove all values from list a, which are present in list b. If a value is present in b, all of its occurrences must be removed from the other

```javascript
arrayDiff([1,2],[1])         // [2]
arrayDiff([1,2,2,2,3],[2])   // [1,3]
arrayDiff([], [4,5])         // []
arrayDiff([3,4], [3])        // [4]
arrayDiff([1,8,2], [])       // [1,8,2]
```

### Exercise No 5
>**Is a number prime?**    
> Define a function that takes one integer argument and returns logical value true or false depending on if the integer is a prime.

```javascript
isPrime(0)   // false   0 is not prime
isPrime(1)   // false   1 is not prime
isPrime(2)   // true    2 is prime
isPrime(73)  // true   73 is prime
isPrime(75)  // false  75 is not prime
isPrime(-1)  // false  -1 is not prime
```

### Exercise No 6
>**Remove Element**
> Given an array nums and a value val, remove all instances of that value in-place and return the new length.
**Do not allocate extra space for another array**, you must do this by **modifying the input array in-place** with O(1) extra memory.

```javascript
removeElement([3,2,2,3], 3)             // 2;
removeElement([0,1,2,2,3,0,4,2], 2)     // 5;
removeElement([2,3,8,0,9,1,0,4,2], 0)   // 7;
```

### Exercise No 7
>**Search Insert Position**   
> Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.
You may assume no duplicates in the array.

```javascript
searchInsert([1,3,5,6], 5)  // 2;
searchInsert([1,3,5,6], 2)  // 1;
searchInsert([1,3,5,6], 7)  // 4;
searchInsert([1,3,5,6], 0)  // 0;
```
