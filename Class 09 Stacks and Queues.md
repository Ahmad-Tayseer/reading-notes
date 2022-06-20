# ***Read: Class 09 - Stacks and Queues***

***

## **Stack definition:**

    A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

***

## **Common terminology for a stack is:**

- Push - Nodes or items that are put into the stack are pushed.

- Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.

- Top - This is the top of the stack.

- Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

- IsEmpty - returns true when stack is empty otherwise returns false.

***

## **Stacks follow these concepts:**

- FILO: First In Last Out

        This means that the first item added in the stack will be the last item popped out of the stack.


- LIFO: Last In First Out

        This means that the last item added to the stack will be the first item popped out of the stack.

### **Stack Visualization:**

![](./Class-08%20images/stack1.png)

1. Push O(1):

![](./Class-08%20images/pushStack3.png)

        ALOGORITHM push(value)

        // INPUT <-- value to add, wrapped in Node internally
        // OUTPUT <-- none

        node = new Node(value)
        node.next <-- Top
        top <-- Node


2. Pop O(1):

![](./Class-08%20images/popStack4.png)

        ALGORITHM pop()
        // INPUT <-- No input
        // OUTPUT <-- value of top Node in stack
        // EXCEPTION if stack is empty

        Node temp <-- top
        top <-- top.next
        temp.next <-- null
        return temp.value

3. Peek O(1):

        ALGORITHM peek()

        // INPUT <-- none
        // OUTPUT <-- value of top Node in stack
        // EXCEPTION if stack is empty

        return top.value

4. IsEmpty O(1):

        ALGORITHM isEmpty()

        // INPUT <-- none
        // OUTPUT <-- boolean

        return top = NULL

***

***

## **Common terminology for a queue is:**

- Enqueue - Nodes or items that are added to the queue.

- Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.

- Front - This is the front/first Node of the queue.

- Rear - This is the rear/last Node of the queue.

- Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.

- IsEmpty - returns true when queue is empty otherwise returns false.


***

## **Queues follow these concepts:**

- FILO: First In First Out

        This means that the first item in the queue will be the first item out of the queue.

- LIFO: Last In Last Out

        This means that the last item in the queue will be the last item out of the queue.

### **Queue Visualization:**

![](./Class-08%20images/Queue.png)

1. Enqueue O(1):

![](./Class-08%20images/Enqueue3.png)

        ALGORITHM enqueue(value)

        // INPUT <-- value to add to queue (will be wrapped in Node internally)
        // OUTPUT <-- none

        node = new Node(value)
        rear.next <-- node
        rear <-- node


2. Dequeue O(1):

![](./Class-08%20images/Dequeue3.png)

        ALGORITHM dequeue()

        // INPUT <-- none
        // OUTPUT <-- value of the removed Node
        // EXCEPTION if queue is empty

        Node temp <-- front
        front <-- front.next
        temp.next <-- null

        return temp.value

3. Peek O(1):

        ALGORITHM peek()

        // INPUT <-- none
        // OUTPUT <-- value of the front Node in Queue
        // EXCEPTION if Queue is empty

        return front.valuee

4. IsEmpty O(1):

        ALGORITHM isEmpty()

        // INPUT <-- none
        // OUTPUT <-- boolean

        return front = NULL

***

[README](README.md)
