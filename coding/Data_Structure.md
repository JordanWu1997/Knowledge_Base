# Data Structures - Computer Science Course for Beginners
- https://www.youtube.com/watch?v=zg9ih6SVACc&list=WL&index=27
- https://www.youtube.com/watch?v=2T-A_GFuoTo

## Outline
- Efficiency
- Basic DS
    - Array
    - ArrayList
- Intermediate DS
    - Stack
    - Queue
    - Linkedlist
    - Doubly-LinkedLists
    - Dictionary
- Tree-based DS
    - Tree
    - Tries
    - Heaps
    - Graphs

## Big O Notation

Efficiency: Number of operation performed in __Worst-case scenario__

Efficiency based on 4 metrics
- Accessing
- Searching
- Inserting
- Deleting

Time Complexity Equation
- Good
    - `O(1)`: Constant. No matter what the size of your data set is
    - `O(log(n))`: Get more efficient as the size of the data set increases
        - e.g. binary search
- Bad
    - `O(n)`: Linear
    - `O(nlog(n))`
    - `O(n^2)`
    - `O(2^n)`: Exponential

## Random Access Data Structures
Elements are independent of others

### Array
A list of __similar__ values (that have same types)

Components
- Name: Name for the array
- Type: Type of information is stored (e.g. string)
- Size: Total amount of elements. __CANNOT BE CHANGED__ after an array is created

Creating Array
- Populate-First Array: Define an array and fill it with elements at the same time
- Populate-Later Array: Create an array by setting an initial size, but __NOT__ fill it with any elements

Numerical Indexes
- Get information of elements within an array
- Replace elements within an array

Arrays as a DS
- Accessing: `O(1)`
    - Due to the fixed size of array
- Searching: `O(n)`
    - Must use linear search
- Inserting: `O(n)`
    - Require to shift every element
- Deleting: `O(n)`
    - Require to shift every element

### ArrayList
Growing array (with dynamic size) which is __resizable__
ArrayList evolves from Array and take advantage of it

Methods built-in for most of the time
- Add Method
    - Append the element to the end of ArrayList
    - Append the element to the index you pass in
- Remove Method
    - Remove the objects at the index you provide
    - Remove the first instance of the object passed into the ArrayList
- Get Method
    - Refer elements within the ArrayList
- Set Method
    - Replace elements within the ArrayList
- Clear Method
    - Clear the ArrayList, deleting entire ArrayList
- toArray Method
    - Convert an ArrayList to an Array

ArrayList as a DS (which is just like Array)
- Accessing: `O(1)`
- Searching: `O(n)`
- Inserting: `O(n)`
- Deleting: `O(nk)`

## Sequential Access Data Structures
Can only be accessed in a particular order
- Each element is dependent on the other

### Stack
A __sequential access data structure__ in which we add/remove elements according to __Last In First Out (LIFO)__ principle

Methods built-in
- Push Method
    - Push an element onto the top of the stack
- Pop Method
    - Remove an element from the top of the stack
- Peek Method
    - Allow you get the value at the top of the stack without removing it
- Contain Methodd
    - Return whether or not the stack contains an object

Stack as a DS
- Accessing: `O(n)`
    - Need to take every elements on top the stack in thee worst case
- Searching: `O(n)`
    - Need to take every elements on top the stack in thee worst case
- Inserting: `O(1)`
- Deleting: `O(1)`

Stack use case
- Recursion
- Undo/Redo
- Back-Paging

### Queue
A __sequential access data structure__ in which we add/remove elements according to __First In First Out (FIFO)__ principle

Method built-in
- Enqueue Method
    - Add an element to the tail of the queue
- Dequeue Method
    - Remove an element from head of the queue
- Peek Method
    - Allow you get the value at the head of the queue
- Contain Method
    - Return whether or not the queue contains an object

Queue as a DS
- Accessing: `O(n)`
- Searching: `O(n)`
- Inserting: `O(1)`
- Deleting: `O(1)`

Queue use case
- Job scheduling
- Printer queuing

### LinkedList
A Sequential access linear data structure in which every element is a separate object called a `Node`, which has two parts
- Data
- Reference (or pointer) which points to the __NEXT__ Node in the List (one-way only)

Data can flow in/out of any point of LinkedList

Creating LinkedList
1. Create head node and point to null
2. Create next node (tail node) and make head node point toward it as the tail node points to null
3. Create next node as new tail node and make last tail node point toward it as the new tail node points to null

Add/Remove to/from Head
Add/Remove to/from Middle
Add/Remove to/from Tail

LinkedList as a DS
- Accessing: `O(n)`
- Searching: `O(n)`
- Inserting:
    - `O(n)`: if not head or tail
    - `O(1)`: for head and tail
- Deleting:
    - `O(n)`: if not head or tail
    - `O(1)`: for head and tail

LinkedList use case
- Backing of other data structures (e.g. stacks, queues, and etc.)
- Playlist

### Doubly-Linked List
A Sequential access linear data structure in which every element is a separate object called a `Node`, which has two parts
- Data
- Reference (or pointer) which points to the __NEXT/PREVIOUS__ Nodes in the List (one-way only)

Doubly-Linked List as a DS
- Accessing: `O(n)`
- Searching: `O(n)`
- Inserting:
    - `O(n)`: if not head or tail
    - `O(1)`: for head and tail
- Deleting:
    - `O(n)`: if not head or tail
    - `O(1)`: for head and tail

Doubly-Linked List use case
- Back and forth functionality
- Undo/Redo, and stack-like functionality

### Dictionary
An abstract data structure which stores data in the form of __key/value pairs__.
Dictionary is also known as Map or Associate Array.
- Every key can only __appear once__ within the dictionary (key is __unique__)
- Each key can only have __ONE value__
- There can be duplicate values within dictionary

#### Hash Table
Dictionaries are built upon Hash Tables, and the key's in our key/value pairs are stored in memory in these hash tables at indexes which are determined by a hash function

#### Hash Function
Function/Algorithm that generates index of key in hash table

#### Hash Collision
If more than one key that has the same index generated by hash function, here comes hash collision

Solution to hash collision
- Open Addressing
    - Move to next free index in hash table
    - Linear Probing: when searching keys, start from the index calculated from hash function and then do linear search
        - Hard to search if the hash table is large and load (occupation) of hash table is high
        - For open addressing strategy, the size of hash table should be larger than the size of keys to be stored
- Closed Addressing
    - Create a linked list to accommodate all keys that have same index in hash table
    - When searching key, start from the index calculated from hash function and then do linked list search
        - Easier to search if the hash table is large and load (occupation) of hash table is high

Dictionary as a DS
- Accessing:
    - `O(n)`
    - `O(1)`: with Hash function that has no collision
- Searching:
    - `O(n)`
    - `O(1)`: with Hash function that has no collision
- Inserting:
    - `O(n)`
    - `O(1)`: with Hash function that has no collision
- Deleting:
    - `O(n)`
    - `O(1)`: with Hash function that has no collision

## Tree Based Data Structures
Tree store data __hierarchically__ as opposed to linearly (e.g. file structure).

### Tree
Tree is an abstract data structures which contains a series of linked node connected together to form a hierarchical representation of information
Like a LinkedList where each node has the option of pointing towards __multiple nodes__

Terminology
- Vertice: A certain node in a tree
- Edge: A connection between nodes
- Root Node: __Topmost__ node of a tree
- Child Node: A certain node which has an edge connecting it to another node one level above itself
- Parent Node: Any node which __has 1 or more child nodes__
- Leaf Node: A node in a tree which does __NOT have any child nodes__
- Height (Tree property): Number of edges the __longest possible path down towards a leaf__
- Depth (Node property): Number of edges required to get __from that particular node to the root node__

Tree use case
- File structure

### Binary Search Tree
Simple variation on the standard tree which has three restrictions
- A node can have __at most 2 children__
- For any given parent node, the child to the left has a value less then or equal to itself and the child to the right has a value greater than or equal to itself
- No 2 nodes can contain the same value

Advantage: search through items in __logarithmic time__
- Go to left if the value we're searching for is less than current node
- Go to right if the value we're searching for is greater than current node

### Trie
Tree-like data structure whose __nodes store letters of an alphabet in the form of characters__
Trie comes from the middle of the word retrieval

Trie use case
- English dictionary
- Autocompletion
- Misspell correction

### Heap
A special tree where all parent nodes compare to their child node's in some specific way by being __more extreme__
- Either greater or less than
- Determines where the data is stored
- Usually dependent on the parent node's value

#### Min-Heap
The value at the __root node of the tree must be the minimum__ amongst all of its children
Recursively for all parents node is the minimum amongst all of its children

#### Max-Heap
The value at the __root node of the tree must be the maximum__ amongst all of its children
Recursively for all parents node is the maximum amongst all of its children

Heap use case
- Heap sorting algorithm
- Priority queues

## Graph
A __nonlinear__ data structure consisting of nodes and edges
- Finite set of nodes (vertices) which are connected by the edges
- Come together to visualize data

### Undirected Graph
A graph in which the __direction__ you traverse the nodes is __NOT important__
- No arrow indication

### Directed Graph
A graph in which the __direction__ you traverse the nodes is __important__
- Arrow indication

### Cyclic Graph
One which contains a path from at least one node back to itself.
__All undirected graphs are cyclical.__

### Acyclic Graph
One which contains __NO path__ from any node which leads back to itself

### Weighted Graphs
Edge that are associated with a numerical value (cost)

### Unweighted Graphs
Edge that are __NOT associated with a numerical value__ (cost)
