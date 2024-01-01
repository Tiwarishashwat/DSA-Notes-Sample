# Data Structure

## Name: Stack

### Insertion (Push): O(1) —> [stack.push(data)]

### Deletion (Pop): O(1)   --> [int data = stack.pop()]

### Updation : First we need to find the element by popping from the top, then update the element and push all the popped elements

#### Best Case —> We want to update the top element. [No pop and Push required so TC will be O(1)]

#### Worst Case —> We want to update the bottom element or the element is not present in stack. [pop all in O(n) time, update in Constant time (if found) and then Push back all elements in O(N) time]

#### Where to keep the popped elements > Use another stack or arrayList, stack is better because it will take care of the order of elements.

## Syntax: 
### Stack<Integer> stack = new Stack<>(); // we can also provide capacity to the constructor
Raw Implementation:

    (Use an array, a size variable and a capacity variable)
    Check if array is full then either increase the capacity or return array is full.
    Insert into array and increase the size,

Below is dummy implementation.
1. Int arr[] = new int[capacity];
2. Int size;
    1. Push(int data){
    2. If (size == capacity-1){
        1. Return stack is full
    3. }
    4. arr[size] = data;
    5. size++
    6. }
       // Similarly implement other functions.

### We can use Stack class of Collections Framework.

### Important functions:
    1. Push
    2. pop
    3. isEmpty
    4. And so on…

## How to iterate?
Use a while loop, until the stack is empty, keep on popping the element and print them.
Use a for loop, but store the size in a variable before…
Can we use Iterator? No, because it will give random order.

# Algorithm:

## Name: Quick Sort

Quicksort is a sorting algorithm that follows the divide-and-conquer approach. It selects a pivot element from the array and partitions the other elements into two subarrays, those less than the pivot and those greater. The process is recursively applied to the subarrays, efficiently sorting the entire array in-place.

### Steps:
* Choose Pivot:
    * Select a pivot element from the array. Common choices include the first, last, or middle element.
* Partitioning:
    * Rearrange the array elements such that elements smaller than the pivot are on the left, and elements greater than the pivot are on the right.
    * The pivot is now in its final sorted position.
* Recursive Sort:
    * Apply QuickSort recursively to the sub-arrays on the left and right of the pivot until the base case (single element or empty array) is reached.
* Combine:
    * No additional combining step is needed for QuickSort, as the array is sorted in place during the partitioning step.

### Time Complexity:
* Average Case (Expected): O(n log n)
* Worst Case: O(n^2)
  The worst-case time complexity occurs when the pivot chosen in each partitioning step consistently results in unbalanced partitions, meaning one partition has significantly more elements than the other. This can happen, for example, when the array is already sorted or nearly sorted, and the first or last element is consistently chosen as the pivot.


# Theory:
## Topic: Polymorphism
### Polymorphism in Java:
Polymorphism allows objects of different classes to be treated as objects of a common base class, promoting flexibility in code design.
There are two main types of polymorphism in Java:
* Compile-time Polymorphism (Static Binding):
    * Achieved through method overloading.
    * Occurs at compile time based on the method signature.
* Runtime Polymorphism (Dynamic Binding):
    * Achieved through method overriding.
    * Occurs at runtime, and the appropriate method is determined during program execution based on the actual object type.

### Advantage:
Enables code reusability and flexibility by allowing the use of a single interface for different types of objects.
### Disadvantage:
May introduce complexity, and understanding code behaviour may require tracing through various classes and methods.


# Problem:
## Minimum number of distinct elements
You will given an array, it may or may not have duplicates, find in how many unique sets we can divide the array.

    Example: [2,4,5,4,1,7,5,7]
    Ans: 3
    First -> [2,4,5,1,7]
    Second -> [4,7,5]
    Third -> [7]


## Brute Force:
Create a boolean array and a set.

Use boolean array to mark if element in given to any of the set,

Use set to add elements.

    // mark all elements as not visited
    // init res to 0
    for(I=0 to N){
    // check if element is visited then continue using bool array
    res++; // increase res whenever we create a new set
    // create a new set
    for(int j=i; to N){
    // check if element is visited or present in the set then continue
    // store the element in the set and mark visited
    }
    }

### Time Complexity: N^2
### Drawback:
We are iterating same elements more than once
We are creating a new set whenever there is a duplicate

### Optimal:
Since duplicates are responsible for creating new sets, we can directly find the most duplicated element
And that will be my answer.
We can use a Hashmap to mark element and frequency.

### Time Complexity: O(N)

Code if needed.
