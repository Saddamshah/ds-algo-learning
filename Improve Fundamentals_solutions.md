### Exercise No 1
> Extract the domain name from a URL

```javascript
const domainName = (url) => {
    return url.replace("https://", "")
    .replace("http://", "")
    .replace("www.", "")
    .split('.')[0]  
}
```

### Exercise No 2
> Create Phone Number

```javascript

```


### Exerise No. 10 
>  Intersection of Two Arrays

```javascript
//======= First Solution =======
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

//======= Second Solution =======
const intersection = (nums1, nums2) => {
  const set1 = new Set(nums1)
  const set2 = new Set(nums2)
  return [...set1].filter(n => set2.has(n))
};

```
