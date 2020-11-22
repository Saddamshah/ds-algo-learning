# Single Linked List

| SR No. | Method Name  |   Method Description   | Time Complexity |  Space Complexity |
|:------:|:------------ |:----------------------| :--------------:|:----------------: |
|  1     | insertAtHead | Adding the node at the beginning of the list | O(1) | O(1)   |
|  2     | removeAtHead | Removing the node at the beginning of the list. | O(1) | O(1)|
|  3     | push         | Adding the node at the end of the list.  | O(N) | O(1)   |
|  4     | pop          | Removing the node at the end of the list. |O(N) | O(1)   |
|  5     | getIndex     | Get the value at specific Index   | O(N) | O(1)   |
|  6     | setIndex     | Update the value at specific Index | O(N) | O(1)   |
|  7     | insertAtIndex | Add node at specific Index | O(N) | O(1)   |
|  8     | removeAtIndex | Remove a node at specific Index | O(N) | O(1)   |
|  9     | search       | Check the node is in the list or not. | O(N) | O(1)   |
|  10    | print         | Print All the node value. | O(N) | O(1)   |
|  11    | reverse       | Reverse all the value In the list. | O(N) | O(1)   |


## In order to create LinkedList We need to create Two Classes.
```Javascript
class Node{
  constructor(value, next){
    this.value = value;
    this.next = next;
  }
}

class LinkedList{
  constructor(){
    this.head = null;
    this.length = 0;
  }
}
```

### 1. insertAtHead
```javascript
LinkedList.prototype.insertAtHead = function(value){
    this.head = new Node(value, this.head);
    this.length++; 
}
```

### 2. removeAtHead
```javascript
LinkedList.prototype.removeAtHead = function(){
    if(!this.head)  return null;
    this.head = this.head.next;  
    this.length--;  
}

```

### 3. push
```javascript
LinkedList.prototype.push = function(value){
    let newNode = new Node(value, null)
    if(!this.head) {
        this.head = newNode;
    } else {
      let current = this.head;
      while(current.next){
        current = current.next;
      }

      current.next = newNode;
    }


    this.length++;
}
```

### 4. pop
```javascript
LinkedList.prototype.pop = function(){
    if(!this.head) return null;
    if(!this.head.next) {
      this.head = null;
    }
    else {
      let prev = this.head;
      while(prev.next){
        if(prev.next.next)  prev = prev.next
        else break;
      }

      prev.next = null;
    }
    
    this.length--;
}
```

### 5. getIndex
```javascript
LinkedList.prototype.getIndex = function(index){
    if(index === 0) return this.head;
    if(index < 0 || index >= this.length) return null;

    let current = this.head;
    for(let i = 1; i <= index; i++){
      current = current.next;
    }

    return current;

}
```

### 6. setIndex
```javascript
LinkedList.prototype.setIndex = function(index, value){
    if(index === 0) return this.head.value = value;
    if(index < 0 || index >= this.length) return null;

    let current = this.head;
    for(let i = 1; i <= index; i++){
      current = current.next;
    }

    current.value = value;
    return current;

}
```

### 7. insertAtIndex
```javascript
LinkedList.prototype.insertAtIndex = function(index, value){
    if(index < 0 || index > this.length) return null;
    if(index == 0) return this.insertAtHead(value);
    if(index == this.length) return this.push(value);
   
    let prev = this.getIndex(index -1);
    prev.next = new Node(value, prev.next) 
    
    
    this.length++;
}
```

### 8. removeAtIndex
```javascript
LinkedList.prototype.removeAtIndex = function(index){
    if(index < 0 || index >= this.length) return null;
    if(index == 0) return this.removeAtHead();
    
    let prev = this.getIndex(index -1);
    let next = prev.next.next;
    prev.next = next;
    
    this.length--;
}
```

### 9. search
```javascript
LinkedList.prototype.search = function(value){
    if(!this.head) return null;
    let current = this.head;
    while(current){
      if(current.value === value) return true;
      current = current.next

    }

    return false;
}
```

### 10. print
```javascript
LinkedList.prototype.print function(){
    let current = this.head;
    let output = ``;
    while(current){
      output = `${output} ${current.value} ->`
      current = current.next;
    }

    console.log(`${output}  null | length ${this.length}`)

  }
}
```

### 11. reverse
```javascript
LinkedList.prototype.reverse = function(){
    let current = this.head;
    let next = null;
    let prev = null;

    while(current !== null){
      next = current.next;
      current.next = prev;
      prev = current;
      current = next;
    }
      this.head = prev;
    return prev;
}
```
