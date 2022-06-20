# Stacks And Queues

## What is a Stack

A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

Common terminology for a stack is :-

- **Push** :- Nodes or items that are put into the stack are pushed
- **Pop** :- Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
- **Top** :- This is the top of the stack.
- **Peek** :- When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
- **IsEmpty** :- returns true when stack is empty otherwise returns false.

## What is the concepts that Stacks follow them ?

- FILO : (First In Last Out) This means that the first item added in the stack will be the last item popped out of the stack.

- LIFO : (Last In First Out) This means that the last item added to the stack will be the first item popped out of the stack.

---

![stack](./img/stack1.png)

---

## Why Pushing a Node onto a stack will always be an O(1) operation?

    because it takes the same amount of time no matter how many Nodes (n) you have in the stack.

## Push steps :-

1. you should have the Node that you want to add.
2. you need to assign the next property of newNode to reference the same Node that top is referencing: prevTopNode.
3. re-assign our reference top to the newly added Node, newNode.

```js
 ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node
```

---

## Pop steps :-

1. The first step of removing Node 5 from the stack is to create a reference named temp that points to the same Node that top points to.
2. re-assign top to the value that the next property is referencing.
3. you may want to make sure that you clear out the next property in your current temp reference. This will ensure that no further references to Node 4 are floating around the heap. This will allow our garbage collector to cleanly and safely dispose of the Nodes correctly.
4. we return the value of the temp Node that was just popped off.

```js
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value
```

---

## peek

```js
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   return top.value
```

---

## isEmpty

```js
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return top = NULL
```

---
---

## What is a Queue?

- Enqueue - Nodes or items that are added to the queue.
- Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
- Front - This is the front/first Node of the queue.
- Rear - This is the rear/last Node of the queue.
- Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
- IsEmpty - returns true when queue is empty otherwise returns false.

## What is the concepts that Queues  follow them ?

- FIFO : (First In First Out) This means that the first item in the queue will be the first item out of the queue.

- LILO : (Last In Last Out) This means that the last item in the queue will be the last item out of the queue.

---

![queues](./img/Queue.png)

---

## Why Enqueue  a Node onto a stack will always be an O(1) operation?

    because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

## Enqueue steps :-

1. First, we should change the next property of Node 4 to point to the Node we are adding Node 5.
2. e-assign the rear reference to point to Node 5.

```js
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node
```

---

## Why Dequeue   a Node onto a stack will always be an O(1) operation?

    because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

## Dequeue steps :-

1. create a temporary reference type named temp and have it point to the same Node that front is pointing too. This means that temp will point to Node 1.
2. re-assign front to the next value that the Node front is referencing. In our visual, this would be Node 2.
3. re-assign the next property on the temp Node to null. (We do this because we want to make sure that all the proper Nodes clear any unnecessary references for the garbage collector to come in later and clean up.)
4. return the value of the temp Node that was just removed.

```js
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
```

---

## peek

```js
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value
```

- We do not re-assign the next property when we peek because we want to keep the reference to the next Node in the queue. This will allow the front to stay in the front until we decide to dequeue

---

## IsEmpty

```js
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return front = NULL
```
