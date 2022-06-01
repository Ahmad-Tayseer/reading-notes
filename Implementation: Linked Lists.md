# Implementation: Linked Lists


## Big O: Analysis of Algorithm Efficiency

### *Definition:*

    Big O(oh) notation is used to describe the efficiency of an algorithm or function. 

    -  This efficiency is evaluated based on 2 factors:

    1. Running Time (also known as time efficiency / complexity: 
    
        The amount of time a function needs to complete.

    2. Memory Space (also known as space efficiency / complexity: 
    
        The amount of memory resources a function uses to store data and instructions.


### ***The 4 Key Areas for analysis:***

### *Input Size:*

    - Input Size refers to the size of the parameter values that are read by the algorithm. 
    
    - This does not simply refer to the number of parameters an algorithm reads, but takes into account the size of each parameter value as well.

    - The letter (n) will be used to refer to the Input Size value.

    - The higher this number, the more likely there will be an increase to Running Time and Memory Space.


### *Units of Measurement:*

*In order to quantify the Running Time in our analysis, we will consider Three Measurements of time:*

    1. The time in milliseconds from the start of a function execution until it ends.

    2. The number of operations that are executed.

    3. The number of “Basic Operations” that are executed.

*In order to quantify Memory Space, we can consider Four Sources of Memory Usage during function run-time:*

    1. The amount of space needed to hold the code for the algorithm.

    2. The amount of space needed to hold the input data.

    3. The amount of space needed for the output data.

    4. The amount of space needed to hold working space during the calculation.


### *Orders of Growth:*

    Order of Growth represents the increase in Running Time or Memory Space.


    - The table below plots an Order of Growth for space and time to a given value (n), with the very first column representing the size of (n). Each row cell contains the value for Running Time or Memory Space. Depending on which factor you are analyzing.

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_2.png)

    Each of these notations represents the relationship of Complexity factor when compared to input size (n). Line charts can be used to better see how (n) effects space and time efficiency: 

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_3.png)

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_4.png)

### *Worst Case, Best Case, Average Case:*

    1. Worst Case: The efficiency for the worst possible input of size (n).

    2. Best Case: The efficiency for the best possible input of size (n).

    3. Average Case: The efficiency for a “typical” or “random” input of size (n).

***

## Linked Lists

### *Definition:*

    It is a sequence of Nodes that are connected or linked to each other. 
    
    - The most defining feature of a Linked List is that each Node references the next Node in the link.

    - There are two types of Linked List - Singly and Doubly.

### *This is what a Singly Linked List looks like:*

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_5.png)

### *Linear data structures:*

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_6.png)

### *Memory management:*

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_7.png)

### *Parts of a linked list:*

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_8.png)

### *Lists for all shapes and sizes:*

![](./Implementation%3A%20Linked%20Lists%20simages/Screenshot_9.png)

***

[README](README.md)



