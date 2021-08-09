# Stacks and Queues


## STACK

Common terminology for a stack is:
    Push - Nodes or items that are put into the stack are pushed
    Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
    Top - This is the top of the stack.
    Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
    IsEmpty - returns true when stack is empty otherwise returns false.


### Here are all of the operations for stack in pseudo code.
``` cs
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value


ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   return top.value


ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return top = NULL
```

Stacks follow the LIFO (Last in, first out) method.

### Queue

Common terminology for a queue is

    Enqueue - Nodes or items that are added to the queue.
    Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
    Front - This is the front/first Node of the queue.
    Rear - This is the rear/last Node of the queue.
    Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
    IsEmpty - returns true when queue is empty otherwise returns false.

A queue is FIFO and LILO, which means that the first item in queue will be the first item out of queue. LILO is same but with last.

### Pseudocode for Queue methods

``` cs
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node

ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value

ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value


ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return front = NULL
```