
# Data Structure Overview

 ##    1.                  Linked List
  * Singly Or Doubly Linked List   
  * push       (Adding the node at the end of the list)
  * pop        (Removing the node at the end of the list)
  * shift      (Removing the node at the beginning of the list)
  * unshift    (Adding the node at the beginning of the list)
  *  get        (Get the value at specific position)
   * set        (Update the value at specific position)
   * insert     (Add node at specific position)
   * remove     (Remove a node at specific position)
   * reverse    (Reverse all the value) 
   
  ##  2.Stack 
  >> LIFO Data structure
Commonly Implement Using linked list
    Push()  (Adding the node at the head of the list)       O(1)
    pop()   (Removing the node at the head of the list)     O(1)
    

## 3.                   Queue

>>   FIFO Data structure
Commonly Implement Using linked list
    enqueue()  (Adding the node at the tail of the list)      O(1)
    dequeue()  (Removing the node at the head of the list)    O(1)
    
## 4.                 Binary Search Tree

>>   Everything right is greater than parent
   Everything left is lesser than parent
   insert()    (Adding the node)                      O(log n)
   find()      (searching the specific node)          O(log n)


## 5.                  BFS  & DFS
>> Method for traversal trees & graphs.
Both have same time complexity O(n)

>>BFS is little costly in term of space because it using extra 
queue data structure.
DFS is not use extra space as well as it not using any extra 
data structure.


## 6.                   Binary Heaps & Priority queue
>> Binary Heaps are type of heaps min & max.
Similarly to a binary Search Tree but some different rules!

>>MaxBinaryHeap : 
     parent node are always largerthe child nodes.
MinBinaryHeap
     parent nodes are always smaller than child nodes. 

  >> insert()  (Adding the element)         O(log n)


## 7. 			Priority queue

>>   Each element with higher priorities are served first.
   before elements does have lower priorities.
   insert()   (Adding the element)       O(log n)

## 8.                     Hash Table 

>> Same as Javascript Object
>>1. create a hast function
>>2. create methods (set & get)
>>3. create table keys & value
>> Insert, Delete, Access   O(1)
>
##  9.                    Graphs

>> addVertex()  =  (create a new vertex(node));
addEdge()    =  (create connection with node);
removeEdge() =  (remove the edge)
removeVertex() = (remove vertex);

## 10. 		Graphs Traversal
>> Is same as Tree traversal we using the same f
DFS & BFS to traversal the graphs
