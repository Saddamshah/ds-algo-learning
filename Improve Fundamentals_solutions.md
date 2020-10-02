### Exercise No 1
> **Extract the domain name from a URL**

```javascript
const domainName = (url) => {
    return url.replace("https://", "").replace("http://", "")
    .replace("www.", "").split('.')[0]  
}
```

### Exercise No 2
> **Create Phone Number**

```javascript
const createPhoneNumber = (number) => {
  let format = "(xxx) xxx-xxx";
  for(let val of number) format = format.replace('x', val);
  return format;
}
```

### Exercise No 3
> **Moving Zeros To The End**

```javascript
const moveZeros = (arr) => {
  let count = 0;
  let index = 0;

  while(index < arr.length - count){
    if(arr[index] === 0){
      arr.splice(index, 1)
      arr.push(0)
      count++;
    }
    index++;
  } 
  
  return arr;
}
```

### Exercise No 4
> **Array.diff**
```javascript
//First Solution 
const arrayDiff = (arr1, arr2) => {
  if(arr1.length === 0 || arr2.length === 0) return arr1;

  for(let i = 0; i < arr1.length; i++){
    let check = arr2.indexOf(arr1[i])
    if(check !== -1){
      arr1.splice(i, 1);
      i--;
    }
  }

  return arr1;
}
```

```javascript
//Second Solution
const arrayDiff = (a, b) => {
  if(a.length === 0 || b.length === 0) return a;
  return a.filter(val => b.indexOf(val) === -1);
}
```

```javascript
//Third Solution
const arrayDiff = (arr1, arr2) => {
  let firstObj  = {};
  let secondObj = {};

  for(let val of arr1){
    firstObj[val] = (firstObj[val] || 0)+1
  }

  for(let val of arr2){
    secondObj[val] = (secondObj[val] || 0)+1
  }

  for(let key in secondObj){
    if(key in firstObj){
      delete firstObj[key]
    }
  }

  return Object.keys(firstObj);  
}
```

### Exerise No. 10 
>  Intersection of Two Arrays

```javascript
//First Solution
const intersection = (nums1, nums2) => {
    if(nums2.length === 0 && nums1.length === 0) {
        return [];
    };
    
    let compaire = {};
    let result   = {};
    
    for(let val of nums2){
        compaire[val] = (compaire[val] || 0)+1
    }
    
    for(let value of nums1){
        if(value in compaire){
            result[value] = (result[value] || 0)+1
        }
    }
    
    return Object.keys(result);
};
```

```javascript
//Second Solution
const intersection = (nums1, nums2) => {
  const set1 = new Set(nums1)
  const set2 = new Set(nums2)
  return [...set1].filter(n => set2.has(n))
};
```
