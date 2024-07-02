---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# some information about your slides, markdown enabled
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply any unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Linked List

Data Structure (Linear)

<style>
h1 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>

---

# Table of Contents

<br>

- [What is linked list?](#what-is-linked-list)
- [Arrays and Linked list](#arrays-and-linked-list)
- [Advantages and disadvantages of linked lists over arrays](#advantages-and-disadvantages-of-linked-lists-over-arrays)
- [Types Linked list](#types-linked-list)
- [Singly / unidirectional linked list](#singly--unidirectional-linked-list)
- [Doubly / bidirectional linked list](#doubly--bidirectional-linked-list)
- [Circular linked list](#circular-linked-list)
- [Linked list in Javascript](#linked-list-in-javascript)
- [Applications of Linked list](#applications-of-linked-list)
- [Questions](#questions)

<style>
h1 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>

---

## What is Linked List?

<br>
<div style="display: flex; justify-content: space-around;">
  <img border="rounded" style="width: 40%; " src="/images/linkedListIllustration.jpg" alt="LinkedListIllustration">
  <img border="rounded" style="width: 55%; " src="/images/linkedList.png" alt="LinkedList">
</div>
<br>

- A linked list is a linear data structure.
- Each element is a separate object, called a node.
- Each node contains data (an integer in this case) and a pointer (or link or reference) to the next node in the sequence.
- The nodes are not in a contiguous memory, the nodes are stored linearly
  <br>
  <em>[Question: How are nodes stored linearly?]</em>
- They are a dynamic data structure, resizable at run-time.

<!--
A linked list is a linear data structure that consists of a series of nodes (they use nodes) connected by pointers.   A linked list is a linear collection of data elements whose order is not given by their physical placement in memory i.e. With linked lists, the data can be anywhere in memory. Instead, each element points to the next.

Nodes are the building block of the linked list. After all, a linked list is a collection of nodes. Each node contains data as well as ~the memory address~ of the next node in the list. The last node, in this case 2, points to a null node. This means the list is at its end.


Even though the nodes are not in a contiguous memory, the nodes are stored linearly through links. Every node has the address of its succeeding node. That is how each node can access its succeeding node. They hold data in individual objects called nodes.

Answer to question.
Every node has the address of its succeeding node. That is how each node can access its succeeding node.
-->
<style>
h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

  em {
    background-color: #6a1b9a;
  }
</style>

<!--
A linked list is a linear data structure that consists of a series of nodes (they use nodes) connected by pointers.   A linked list is a linear collection of data elements whose order is not given by their physical placement in memory i.e. With linked lists, the data can be anywhere in memory. Instead, each element points to the next.

Nodes are the building block of the linked list. After all, a linked list is a collection of nodes. Each node contains data as well as ~the memory address~ of the next node in the list. The last node, in this case 2, points to a null node. This means the list is at its end.


Even though the nodes are not in a contiguous memory, the nodes are stored linearly through links. Every node has the address of its succeeding node. That is how each node can access its succeeding node. They hold data in individual objects called nodes.

Answer to question ~
Every node has the address of its succeeding node. That is how each node can access its succeeding node.
-->

---

## Arrays and Linked list

Lets say we have the following list of todos - Brunch, Bocce, Tea

<br>

<div style="display: flex; justify-content: space-around; flex-wrap: wrap;">
  <img border="rounded" style="width: 23%; margin: 1%;" src="/images/array1.png" alt="Array 1 ">
  <img border="rounded" style="width: 23%; margin: 1%;" src="/images/array2.png" alt="Array 2">
  <img border="rounded" style="width: 23%; margin: 1%;" src="/images/list1.png" alt="List 1">
  <img border="rounded" style="width: 23%; margin: 1%;" src="/images/list2.png" alt="List 2">
</div>
<br>

- Data structure - array is contiguous while linked list is non-contiguous.
- Memory allocation - array is static while linked list is dynamic.
- Insertion and deletion - inefficient in array but efficient in linked list.
- Access - Random in array while sequential in linked list.

<!--
Using an array means all the tasks are stored contiguously (right next to each other) in memory. If by chance the array needs to grow, the data would be moved to a new memory which would be doubled by the previous stated memory size.

In a linked list, data can be stored anywhere in memory. The key is that each element (or node) contains a reference (or pointer) to the next node in the sequence. This flexibility allows linked lists to utilize available memory more efficiently compared to arrays.

For example, if you need to store four elements but don't have four contiguous memory slots available, a linked list can still accommodate these elements by storing them in separate locations. As long as each node correctly references the next node, the linked list will function properly. This contrasts with arrays, which require a contiguous block of memory. If there isn't enough contiguous space, the array cannot be allocated, which can lead to inefficient memory usage.

By using linked lists, the issue of needing contiguous memory is avoided, allowing for dynamic and flexible memory allocation. This makes linked lists particularly useful for applications where memory allocation and deallocation happen frequently.
-->

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--

-->

---

## Advantages and disadvantages of linked lists over arrays.

<br>

### Advantages

Unlike arrays, linked lists are a dynamic data structure that can be resized at run-time without needing to reallocate or reorganize the entire structure; Linked lists allow for dynamic memory allocation. Nodes are not stored contiguously in memory, so they can be located anywhere in the memory which is beneficial for implementing other abstract data types such as lists, stacks, and queues;Insertion and deletion operations are efficient and can be easily implemented, particularly in the middle of the list.

### Disadvantages

Search operations are slower in linked lists compared to arrays; Linked lists use more memory than arrays because of the storage of additional pointers (references) in each node; The CPU cannot effectively cache the contents of a linked list as well as it can for arrays. This is because the nodes of a linked list can be at arbitrary, possibly far apart locations in memory, leading to poor performance; Unlike arrays, random access of data elements is not allowed in linked lists. Nodes are accessed sequentially starting from the head (the first node).

- The main benefit of a linked list over an array is the ease of inserting and removing elements and the main drawback is the slower search operations and higher memory usage due to the additional pointers.

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>

<!--
It is dynamic - The size of memory can be allocated or de-allocated at run time based on the operation insertion or deletion..

The insertion and deletion of elements are simpler than arrays since no elements need to be shifted after insertion and deletion, Just the address needed to be updated.

Linked List is a dynamic data structure the size increases or decreases as per the requirement so this avoids the wastage of memory.
-->

---

## Types Linked list

<br>

<img border="rounded" style="width: 65%" src="/images/differentTypesOfLinkedList.webp" alt="DifferentTypesOfLinkedList">
<br>

- Singly / unidirectional linked list.
- Double / bidirectional linked list.
- Circular linked list.
- Circular doubly linked list.

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

## Singly / unidirectional linked list

<br>
<img border="rounded" style="width: 65%" src="/images/unidirectionalLinkedlist.png" alt="UnidirectionalLinkedlist">

<br>

- Each node contains only one pointer to the next node.
- Traversal: Allowed only in one direction (forward).
- Memory Efficiency: Requires only one reference per node.
- Complexity: Easier insertion and deletion, as only one reference needs updating.

<br>

### Time and Space Complexity

- Traversal, Insertion at the End, Deletion at the End, Insertion at Any Point, Deletion at Any Point --> <b>O(n) time, O(1) space.</b>
- Insertion at the Beginning, Deletion at the Beginning --> <b>O(1) time, O(1) space.</b>

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}


  img {
    background-color: white;
  }

  b {
     color: #6a1b9a;
  }
</style>

<!--
For singly linked lists, the time complexity for insertion or deletion at any arbitrary point in the list is O(n) because it may require traversing the list to locate the desired position. The space complexity remains O(1) since no additional space proportional to the input size is required for these operations.
-->

---

## Doubly / bidirectional linked list

<br>
<img border="rounded" style="width: 65%" src="/images/bidirectionalLinkedList.png" alt="BidirectionalLinkedList">
<br>

- Each node contains two pointers, one to the next node and one to the previous node.
- Traversal: Allows bidirectional traversal (forward and backward).
- Memory Efficiency: Requires more memory due to two references per node.
- Complexity: Insertion and deletion operations may require updating references in both directions which can increase the complexity and potentially impact performance.

<br>

### Time and Space Complexity

- Traversal, Insertion at Any Point, Deletion at Any Point --> <b> O(n) time, O(1) space</b>
- Insertion at the Beginning, Insertion at the End, Deletion at the Beginning, Deletion at the End --> <b>O(1) time, O(1) space</b>

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

  img {
    background-color: white;
  }

  b {
     color: #6a1b9a;
  }
</style>

<!--
Doubly linked lists typically require more memory compared to singly linked lists because each node contains two references (pointers) — one for the next node and one for the previous node. This additional memory overhead per node can impact the overall memory efficiency, especially for large lists.

For doubly linked lists, note that insertion and deletion at the end have improved time complexity (O(1)) compared to singly linked lists which has O(n), since they can maintain a reference to the last node.

In a singly linked list, each node contains a reference to the next node in the sequence, but not to the previous node. Therefore, to perform an insertion or deletion at the end of the list, you need to traverse the entire list from the beginning to find the last node. This traversal takes O(n) time, where n is the number of nodes in the list.

However, in a doubly linked list, each node contains references to both the next and the previous nodes. Additionally, a doubly linked list can maintain a reference to the last node in the list (often called the "tail"). This reference allows direct access to the last node without the need for traversal.
-->

---

## Circular linked list

<br>
<img border="rounded" style="width: 65%" src="/images/circularLinkedList2.png" alt="CircularLinkedList">
<br>

- The last node points to the first node, forming a loop.
- Traversal: Allows continuous traversal in a loop.
- Memory Efficiency: Similar to singly linked lists with one pointer per node.
- Complexity: Moderate due to maintaining the circular structure.

<br>

### Time and Space Complexity

- Traversal, Insertion at the End, Deletion at the End, Insertion at Any Point, Deletion at Any Point --> <b>O(n) time, O(1) space</b>
- Insertion at the Beginning, Deletion at the Beginning --> <b>O(1) time, O(1) space</b>

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

  img {
    background-color: white;
  }

  b {
     color: #6a1b9a;
  }
</style>

<!--
In a circular linked list, there is no null pointer at the end; instead, the last node points back to the first node, creating a loop structure. This looping behavior allows for continuous traversal through the list.

Imagine a train line that forms a loop, with passengers boarding and exiting at various stations along the way. This loop represents a circular linked list, where each station is a node and the train continuously travels around the loop, picking up and dropping off passengers.

 The loop ensures continuous traversal without an end point, and passengers (data) can be added or removed at any station (node). The circular linked list offers advantages in certain applications but requires careful handling of pointers and memory management to maintain its circular structure and prevent issues such as infinite loops.
-->

---

## Linked list in Javascript

Almost every programming language has a built-in linked list but JavaScript does not have a built-in linked list data structure like some other programming languages (e.g., Java's LinkedList or C++'s std::list).

Since linked lists aren’t a native data structure in JavaScript, so to implement it, you need to create a custom class and object for it. Now this will mean that the differences and benefits mentioned above may not be completely accurate since, under the hood, it would be treated as a different data structure.

### What linkedlist looks like in JS

<br>

<img border="rounded" style="width: 40%; max-height: 80%" src="/images/linkedListObject.png" alt="What linkedlist looks like in JS" >

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

## What a node and linkedlist ( collection of nodes) looks like

<br>
<img border="rounded" style="width: 40%; max-height: 60%" src="/images/nodeIllustration.png" alt="A single node illustration" >

<br>
<br>

<img border="rounded" style="width: 70%; max-height: 60%" src="/images/linkedListIllustration.png" alt="Linked list with four nodes illustration" >

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

## Creating linkedlist in JS (using classes) - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}


</style>

---

## Appending a node to the linkedlist

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistAppend.png" alt="Linked list append illustration" >

<p> When the list is not empty, the diagram above illustrates the process: a temporary pointer called  <em>prev</em> is created to traverse the list and locate the last node, allowing the new node to be appended. If the list is empty, the new node is set as the head. </p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

 em {
    background-color: #6a1b9a;
  }
</style>

---

## Appending a node - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(30);
list.append(40);

// NOTE- FOUR NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log(printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}


</style>

---

## Prepending a node to the linkedlist

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistPrepend.png" alt="Linked list prepend illustration" >

<p>The diagram above shows the prepend process: the new node is added and set as the head of the list. </p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

</style>

---

## Prepending a node - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   PREPEND i.e. add new node to be start of the linked list
  prepend(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // the new node would point to the head before the prepend
      // operation so it can become the new head (Step 2 in the illustration)
      newNode.next = this.head;

      //   the new node becomes the head (Step 3 in the illustration)
      this.head = newNode;
    }

    this.size++;
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.prepend(30);
list.prepend(20);
list.prepend(10);
list.prepend(05);

// NOTE- FOUR NODES HAVE BEEN PREPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log(printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}


</style>

---

## Inserting a node at a given index of the linkedlist

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistInsert01.png" alt="Linked list inserting at a given index illustration" >

<p>The diagram above shows the insertion process: <em>Inserting at index 0 is the same as prepending.</em> When the insertion index is greater than 0, a temporary pointer called <em>prev</em>  traverses to the node before the desired insertion position. In this case, to insert at index 2, prev stops at index 1. </p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

 em {
    background-color: #6a1b9a;
  }
</style>

---

## Inserting a node at a given index to the linkedlist (contd.)

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistInsert02.png" alt="Linked list inserting at a given index illustration" >

<p> Once in position, the prev pointer is updated to point to the new node, and the new node points to the next node, forming an updated linked list.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

 em {
    background-color: #6a1b9a;
  }
</style>

---

## Inserting a node at a given index - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }

  //   INSERT AT A GIVEN INDEX (accepts the value to be inserted and the index)
  insert(value, index) {
    // the index you want to insert into needs to be valid
    if (index < 0 || index > this.size) {
      return;
    }

    // inserting a node at index 0 is the same as prepending
    if (index === 0) {
      this.prepend(value);
    } else {
      const newNode = new Node(value);

      // prev is a temporary pointer to point to the node before the index
      // we want to insert the new node (step y in the illustration)
      let prev = this.head;
      for (let i = 0; i < index - 1; i++) {
        prev = prev.next;
      }

      //   once we get the prev, we need to reorganize the node
      // i.e. point the new node's pointer to the next node (index 2 in the illustration)
      // and the previous node's pointer points to the new node
      newNode.next = prev.next;
      prev.next = newNode;

      this.size++;
    }
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(30);

// NOTE- THREE NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list - ", printResult);

list.insert(25, 2);

// NOTE- A NODE WAS INSERTED INTO TO THE LIST AT INDEX 2
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list after inserting 25 at position 2 - ", printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}


</style>

---

## Removing a node at a given index of the linkedlist

<img border="rounded" style="width: 65%; max-height: 85%" src="/images/LinkledlistRemove03.png" alt="Linked list removal at index zero illustration" >

<p>The diagram above illustrates the removal of the node at index 0 (the first node): The node at index 1 becomes the new head, and the first node is removed.  </p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

</style>

---

## Removing a node at a given index greater than 0

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistRemove01.png" alt="Linked list removal at a given index greate then zero illustration" >

<p>The diagram above illustrates the removal process at an index greater than 0: A temporary pointer <em>prev</em> is created to traverse to the node before the one we want to remove. The node to be removed is assigned to another temporary pointer <em>remv</em>. </p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

 em {
    background-color: #6a1b9a;
  }
</style>

---

## Removing a node at a given index greater than 0 (contd.)

<img border="rounded" style="width: 60%; max-height: 80%" src="/images/LinkledlistRemove02.png" alt="Linked list removal at a given index greate then zero illustration" >

<p>The prev pointer then skips the removed node and points to the node after it, reconnecting the list and forming an updated list.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }
</style>

---

## Removing a node at a given index - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }

  //   REMOVE A NODE GIVEN THE INDEX
  removeNode(index) {
    // the index you want to remove from the list needs to be valid
    if (index < 0 || index > this.size) {
      return null;
    }

    let removedNode;
    if (index === 0) {
      removedNode = this.head;
      this.head = this.head.next;
    } else {
      // prev is a temporary pointer to point to the node before the index
      // we want to remove the node (step y in the illustration)
      let prev = this.head;
      for (let i = 0; i < index - 1; i++) {
        prev = prev.next;
      }

      // once we get the prev, we need to reorganize the node
      // i.e. point the prev node's pointer to the node after removal (index 2 in the illustration)
      removedNode = prev.next;
      prev.next = removedNode.next;
    }

    this.size--;
    return removedNode.value;
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(25);
list.append(30);

// NOTE- FOUR NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list - ", printResult);

list.removeNode(2);

// NOTE- A NODE WAS REMOVED FROM THE LIST AT INDEX 2
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list after the node at index 2 - ", printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}

</style>

---

## Removing a node based on its value rather than its index - CODE

<em>The previous method removes a node using its index, whereas this method removes a node based solely on its value, if present. </em>

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }

  //   REMOVE A NODE GIVEN THE VALUE
  removeUsingValue(value) {
    if (this.isEmpty()) {
      return null;
    }

    // if the value is the first node
    if (this.head.value === value) {
      this.head = this.head.next;
      this.size--;
      return `Value ${value} has been successfully removed`;
    } else {
      // prev is a temporary pointer to point to the node before the index
      // we want to remove the node (step y in the illustration)
      let prev = this.head;
      while (prev.next && prev.next.value !== value) {
        prev = prev.next;
      }

      // once we get the prev, we need to reorganize the node (index 2 in the illustration)
      if (prev.next) {
        const removedNode = prev.next;
        prev.next = removedNode.next;
        this.size--;
        return `Value ${value} has been successfully removed`;
      }

      return null;
    }
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(25);
list.append(30);

// NOTE- FOUR NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list - ", printResult);

list.removeUsingValue(25);

// NOTE- A NODE WITH VALUE 25 WAS REMOVED FROM THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list after removing node with value 25 - ", printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}


.slidev-monaco-container {
  @apply overflow-scroll max-h-screen ;
  max-height: 400px;

}

</style>

---

## Searching for a value in the list - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }

  //   SEARCH FOR A VALUE
  //   return -1 if not present or return the index of the value
  search(value) {
    if (this.isEmpty()) {
      return null;
    }

    let i = 0;
    let curr = this.head;
    while (curr) {
      if (curr.value === value) {
        return i;
      }

      curr = curr.next;
      i++;
    }

    return -1;
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(25);
list.append(30);

// NOTE- FOUR NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list - ", printResult);

let valueToSearch = list.search(22);
let valuePresent = valueToSearch !== -1 ? true : false;
// 22 is not in the list
console.log("Is 22 present in the list? - ", valuePresent);

valueToSearch = list.search(25);
valuePresent = valueToSearch !== -1 ? true : false;
// 25 is in the list
console.log("Is 25 present in the list? - ", valuePresent);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}


.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}

</style>

---

## Reversing the list

<br/>

<img border="rounded" style="width: 65%; max-height: 90%" src="/images/LinkedListReverse.png" alt="Linked list reversal illustration" >

<br/>

<p>This is a summary illustration of what happens during reversal.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }
</style>

---

## Reversing the list - explanation

<br/>

<img border="rounded" style="width: 65%; max-height: 90%" src="/images/LinkedListReverse01.png" alt="Linked list reversal illustration" >

<br/>

<p>Two temporary pointers, <em>prev</em> initialized to null, and <em>curr</em>, are created.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

  em {
    background-color: #6a1b9a;
  }
</style>

---

## Reversing the list - explanation (contd.)

<br/>

<img border="rounded" style="width: 50%; max-height: 65%" src="/images/LinkedListReverse02.png" alt="Linked list reversal illustration" >

<br/>

<p>Additionally, two other pointers, <em>curr</em> and <em>next</em>, are instantiated. Curr holds the node currently being processed. The reversal proceeds node by node: Curr flips the current node to point to prev (which is null initially for the first node), and next holds the next node to be reversed. After the first reversal, prev, curr, and next all move to their next nodes so the process can repeat until the entire list is reversed.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

  em {
    background-color: #6a1b9a;
  }
</style>

---

## Reversing the list - explanation (contd.)

<br/>

<img border="rounded" style="width: 65%; max-height: 90%" src="/images/LinkedListReverse03.png" alt="Linked list reversal illustration" >

<br/>

<p>After completing all reversals, when curr points to null, prev becomes the new head of the list.</p>

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
  }

  em {
    background-color: #6a1b9a;
  }
</style>

---

## Reversing the list - CODE

```js {monaco-run}
// NODE CLASS - the fragment of a linkedlist
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

// LINKED LIST CLASS
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  getSize() {
    return this.size;
  }

  // PRINT THE VALUE IN THE LINKEDLIST
  print() {
    if (this.isEmpty()) {
      return "List is empty";
    } else {
      // curr is a temporary pointer
      let curr = this.head;
      let listValues = "";

      //   while current is not null i.e. it  has a value
      while (curr) {
        listValues += `${curr.value} `;

        // to get access to the next nodes value
        curr = curr.next;
      }

      return listValues;
    }
  }

  //   APPEND i.e. add new node to be end of the linked list
  append(value) {
    const newNode = new Node(value);

    if (this.isEmpty()) {
      this.head = newNode;
    } else {
      // prev is a temporary pointer
      let prev = this.head;

      //   the while loop would exit at the last node where next points to null
      while (prev.next) {
        prev = prev.next;
      }

      //   the last node would point to the new node
      prev.next = newNode;
    }

    this.size++;
  }

  reverse() {
    let prev = null;
    let curr = this.head;
    while (curr) {
      let next = curr.next;
      curr.next = prev;
      prev = curr;
      curr = next;
    }
    this.head = prev;
  }
}

// NOTE- THE LIST IS PRESENTLY EMPTY
const list = new LinkedList();
let isListEmpty = list.isEmpty();
let listSize = list.getSize();
let printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);

list.append(10);
list.append(20);
list.append(25);
list.append(30);

// NOTE- FOUR NODES HAVE BEEN APPENDED TO THE LIST
isListEmpty = list.isEmpty();
listSize = list.getSize();
printResult = list.print();

console.log("Is the list empty? ", isListEmpty);
console.log("The list size is - ", listSize);
console.log("The list - ", printResult);

list.reverse();

printResult = list.print();
console.log("The list after reversal - ", printResult);
```

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}


.slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}

</style>

---

## Applications of Linked list

<br>

- Linked lists can be used to implement stack, queue, graph, hash maps and other abstract data structures.
- Useful in applications such as web browsers and music players.
- Can represent graphs and dynamically allocate/de-allocate memory.
- In a web browser, the history can be stored as a linked list for easy navigation.
- In a music player, the playlist can be a linked list for easy song traversal.

<!--
For example, in a web browser, the browser history can be stored as a linked list. Each page visited can be represented by a node, with the link pointing to the next page visited. This allows for easy navigation through the history, by simply traversing the linked list.

Similarly, in a music player, the playlist can be represented as a linked list. Each song can be represented by a node, with the link pointing to the next song in the playlist. This allows for easy navigation through the playlist, by simply traversing the linked list.
-->

<style>
    h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

## Questions...

<br>
<h4>Am I really ever going to use LinkedLists in software engineering, especially in frontend development?</h4>

<style>
  h2 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

<img border="rounded" style="width: 100%" src="/images/thankYou.jpeg" alt="Thank You">

<style>
h1 {
  background-color: #6a1b9a;
  background-image: linear-gradient(45deg, #9c27b0 10%, #4a148c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>
