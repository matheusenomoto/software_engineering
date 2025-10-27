# Data Structures and Algorithms

## Reference
**Hands-On Data Structures and Algorithms with Python - Basant Agarwal**

## Table of Contents
1. [Data Types and Data Structures](#data-types-and-data-structures)
2. [Introduction to Algorithm Design](#introduction-to-algorithm-design)
3. [Algorithm Design Techniques and Strategies](#algorithm-design-techniques-and-strategies)
4. [Linked Lists](#linked-lists)
5. [Stacks and Queues](#stacks-and-queues)
6. [Trees](#trees)
7. [Heaps and Priority Queues](#heaps-and-priority-queues)
8. [Hash Tables](#hash-tables)
9. [Graphs and Algorithms](#graphs-and-algorithms)
10. [Search](#search)
11. [Sorting](#sorting)
12. [Selection Algorithms](#selection-algorithms)
13. [String Search Algorithms](#string-search-algorithms)

### Data Types and Data Structures

**Basic data types**

The most basic data types are numerical and boolean.

**Numerical**

Store numerical values. the whole values, floating point and complexes belong to this type of data.

- **integer (int)**: The interpreter considers a decimal digit sequence as a decimal value, such as integers 43, 10000, or -26
- **float**: Considers a number that has a floating point value as a float type; It is specified with a point
- **complex**: It is represented with the use of floating point values. It contains an orderly pair, a + Ib. Here, A and B represent real numbers and I represents the imaginary component.

**Boolean**

This type provides a true or false value and checks if any instruction is true or false.

```sh
True != False
```
**Sequence**

They are used to store multiple values in the same variable in an organized and efficient way. There are four basic types of sequence: string, range, lists and tuplas.

- **strings**: It is a sequence of immutable characters represented with quotes that can be simple, double, or triple.
```python
str_1 = 'hello world'
```
- **range**: It is a sequence of unchanging numbers. It is mainly used in loops for and while.
```python
range(start, stop, step)
```
- **lists**: Python lists are used to store multiple items in the same variable.
```python
list_1 = [7,'south', 9, 'west', 13, 'Europe']
```
- **tuples**: Tuples are used to store multiple items in the same variable. It is a reading collection only in which data is ordered (zero base indexation) and unchanged/unchanging.
```python
tuple_1 = (7,'south', 9, 'west', 13, 'Europe')
```

**Complex data types**
- **dictionaries**: A python dictionary is one of the important types of data, which is similar to a list, in the sense that it is also a collection of objects. It stores the data in pairs {key, value}. O The key should be a type of unchanging data and hashable and i vakir oide be any arbitrary python object.
```python
dict_1 = {
    <key>: <value>,
    <key>: <value>,
    ...
    ...
    ...
    <key>: <value>
}
```
- **sets**: A set in Python is a hashable collection of objects. It is iterable, mutable, and has unique elements. The order of the elements is also undefined. While adding and removing items is permitted, the items
themselves exist within the set and must be immutable and hashable.
```python
set_1 = {'algorithm', 'structure', 'data'}
```
- **frozenset**: It is an internal data structure, which is in every respect exactly like a set, except that it is immutable.
```python
frozen_set_1 = frozenset(['algorithm', 'structure', 'data'])
```

**Python collections module**

The collections module provides several types of containers, which are objects used to store different objects and provide a way for us to access them.

- **namedtuple**: Creates a tuple with named fields like regular tuples.
- **deque**: A doubly linked list that provides efficient insertion and removal of items at both ends of the list.
- **defaultdict**: A dictionary subclass that returns default values for missing keys.
- **Chain Map**: A dictionary that merges several dictionaries.
- **Counter**: A dictionary that returns the counts corresponding to its objects/keys.
- **UserDict UserList UserString**: These data types are used to add more functionality to your base data structure, such as dictionary, list, and string. We can subclass them to obtain a custom dict/list/string.

<img width="1149" height="353" alt="python_data_types_tree_01" src="https://github.com/user-attachments/assets/df311740-4b9d-49f5-8f1f-3d28ca8fabaa" />

<img width="537" height="697" alt="python_data_types_tree_02" src="https://github.com/user-attachments/assets/9031e7c5-f97c-4578-9d45-6f04467d4c31" />

### Introduction to Algorithm Design

**Introduction to Algorithms**

An algorithm is a sequence of steps that must be followed to complete a specific task/question.

<img width="411" height="127" alt="algorithm" src="../img/algorithm.png" />

**Analysis of the unfolding of an algorithm**

Generally, the time performance of the algorithm is measured by the size of your input data, N, and the time and memory space used by it.

**Time complexity**

The time complexity of the algorithm is how long it takes to run on a computer system to produce output. The purpose of analyzing the time complexity of the algorithm is to determine, for a specific problem and more than one algorithm, which of the algorithms is most efficient in relation to the time required for its execution. The execution time of the algorithm is the sum of the time required by all instructions.

```python
def linear_search(arr, key):
    for i in range(len(arr)):
        if arr[i] == key:
            return i
    return -1
```

**Asymptotic notation**

When analyzing the time complexity of an algorithm, the growth rate (order of growth) is very important when the input size is large. When the input size becomes large, we only consider the higher-order terms and ignore irrelevant terms.

- **Big-Theta(Θ) notation**: Represents the worst-case runtime complexity with a tight bound.
- **Big-O(O) notation**: Represents the worst-case runtime complexity with an upper bound, which ensures that the function never grows faster than the upper bound.
- **Big-Omega(Ω) notation**: Represents the lower bound on an algorithm's execution time. It measures the best time for the algorithm to execute.

**Theta notation**

$T(n) = \Theta(F(n))$

**Big-O notation**

$T(n) = O(F(n))$

**Omega notation**

$T(n) = \Omega(F(n))$

### Algorithm Design Techniques and Strategies

**Algorithm Design Techniques**

It is a powerful tool for visualizing and clearly understanding precisely formulated real-world problems. Brute-force approaches test all possible solution combinations to solve a problem. This approach can provide useful solutions for limited input sizes, but becomes very inefficient as the input size increases. Design technique guidelines also help to easily develop new algorithms for complex problems. There are several algorithm design paradigms.

**Recursion**

Calls itself repeatedly to solve the problem until a specific condition is met. Each recursive call generates another recursive call.

* **Base Case**
    * They tell the recursion when it should end, meaning that the recursion will stop when the base condition is met.
* **Recursive Case**
    * The function calls itself recursively and so we move towards the base criteria.

<img width="616" height="340" alt="algorithm_recursive_case" src="https://github.com/user-attachments/assets/9fceb609-85ab-4a16-bfe4-43b726e7e93a" />

**Divide and Conquer**

The divide-and-conquer paradigm divides a problem into smaller subproblems and solves them; finally, it combines the results to obtain a globally optimal solution. In divide-and-conquer design, the problem is divided into two smaller subproblems, with each subproblem solved recursively.

* Binary search
* Merge sort
* Quick sort
* Fast multiplication algorithm
* Strassen matrix multiplication
* Closest pair of points

* **binary search**
    * First, it compares the search element with the middle element of the list. If the search element is smaller than the middle element, the half of the list with elements larger than the middle element is discarded. The process is repeated recursively. With each iteration, half of the search space is discarded.

<img width="454" height="421" alt="algorithm_binary_search" src="https://github.com/user-attachments/assets/d5e13080-b74d-4728-91f1-8750f3ef6550" />

* **merge sort**
    * Concept: Divide the list into halves recursively, sort each half, and merge them back together in sorted order.
    * Time Complexity: O(n log n) in all cases
    * Stability: Stable
    * Use Case: Great for large datasets and linked lists.

**Dynamic Programming**

It's the most powerful design technique for solving optimization problems. These problems typically have many possible solutions. It's based on the intuition of the divide-and-conquer technique. Dynamic programming problems have two important characteristics.

* **optimal substructure**
    * Given a problem, if the solution can be obtained by combining the solutions of its subproblems, the problem is said to have an optimal substructure. For example, the i-th Fibonacci number in its seriescan be calculated from the i-th -1 and the i-th -2.
* **overlapping subproblems**
    * When an algorithm needs to repeatedly solve the same subproblem, this happens because the problem has overlapping subproblems.

**Greedy Algorithms**

They involve optimization and combinatorial problems. The goal is to obtain the optimal solution from many possible solutions at each stage. The goal is to obtain the local optimal solution, which may ultimately lead to the global optimal solution.

* **shortest path**
    * The shortest path problem requires us to find the shortest possible route between nodes in a graph. Dijkstra's algorithm is a very popular method for solving this problem using the greedy approach.

<img width="395" height="203" alt="algorithm_shortest_path" src="https://github.com/user-attachments/assets/8a48e84e-c661-410d-a5eb-4af994dc5943" />

* **Dijkstra Algorithm**
    * It is used in Internet routing protocols, primarily in link-state protocols. The main protocols that use this algorithm are:
    * **OSPF (Open Shortest Path First)**
        * Category: Internal Routing Protocol (IGP).
        * Dijkstra's Usage: Each router calculates the shortest path tree to all other routers in the network based on link state information.
        * Resulting tree: SPF (Shortest Path First) tree.
        * Function: Determine the best route to each destination in the AS (Autonomous System). 
    * **IS-IS (Intermediate System to Intermediate System)**
        * Category: Interior Routing Protocol (IGP), widely used in provider networks.
        * Use of Dijkstra: Also uses a variation of the SPF algorithm to calculate the best routes based on a link-state database.
        * Similarity to OSPF: Both are link-state protocols and share similar operating principles.
* **Bellman-Ford**
    * Find the shortest path from a single source to all vertices, and it handles negative weights. Also detects negative weight cycles.

```python
# Define a weighted graph using an adjacency list (dictionary of dictionaries)
graph = dict()
graph['A'] = {'B': 5, 'D': 9, 'E': 2}
graph['B'] = {'A': 5, 'C': 2}
graph['C'] = {'B': 2, 'D': 3}
graph['D'] = {'A': 9, 'F': 2, 'C': 3}
graph['E'] = {'A': 2, 'F': 3}
graph['F'] = {'E': 3, 'D': 2}

# Initialize the shortest path table:
# Each node maps to a list: [shortest_distance_from_origin, previous_node_in_path]
table = {
    'A': [0, None],               # Distance from A to A is 0
    'B': [float('inf'), None],   # Unknown distances are set to infinity
    'C': [float('inf'), None],
    'D': [float('inf'), None],
    'E': [float('inf'), None],
    'F': [float('inf'), None]
}

# Constants for easier index access
DISTANCE = 0
PREVIOUS_NODE = 1
INFINITY = float('inf')

# Get the current shortest known distance to a given vertex
def get_shortest_distance(table, vertex):
    shortest_distance = table[vertex][DISTANCE]
    return shortest_distance

# Update the shortest distance to a vertex
def set_shortest_distance(table, vertex, new_distance):
    table[vertex][DISTANCE] = new_distance

# Set the previous node for a given vertex (used for path reconstruction)
def set_previous_node(table, vertex, previous_node):
    table[vertex][PREVIOUS_NODE] = previous_node

# Get the edge weight between two connected vertices
def get_distance(graph, first_vertex, second_vertex):
    return graph[first_vertex][second_vertex]

# Get the next unvisited node with the smallest known distance
def get_next_node(table, visited_nodes):
    # All unvisited nodes
    unvisited_nodes = list(set(table.keys()).difference(set(visited_nodes)))
    # Start with first unvisited node as the min
    assumed_min = table[unvisited_nodes[0]][DISTANCE]
    min_vertex = unvisited_nodes[0]
    
    # Find the unvisited node with the smallest distance
    for node in unvisited_nodes:
        if table[node][DISTANCE] < assumed_min:
            assumed_min = table[node][DISTANCE]
            min_vertex = node
    
    return min_vertex

# Main function to compute the shortest paths from origin to all other nodes
def find_shortest_path(graph, table, origin):
    visited_nodes = []          # Keep track of processed nodes
    current_node = origin       # Start at the origin
    starting_node = origin

    while True:
        adjacent_nodes = graph[current_node]
        
        # If all adjacent nodes are visited, move on
        if set(adjacent_nodes).issubset(set(visited_nodes)):
            pass
        else:
            # Get only the adjacent nodes not yet visited
            unvisited_nodes = set(adjacent_nodes).difference(set(visited_nodes))
            for vertex in unvisited_nodes:
                distance_from_starting_node = get_shortest_distance(table, vertex)
                
                # Special case: if we're at the starting node and this vertex is being visited for the first time
                if distance_from_starting_node == INFINITY and current_node == starting_node:
                    total_distance = get_distance(graph, vertex, current_node)
                else:
                    # General case: calculate distance through the current node
                    total_distance = get_shortest_distance(table, current_node) + get_distance(graph, current_node, vertex)
                
                # If the newly calculated path is shorter, update it
                if total_distance < distance_from_starting_node:
                    set_shortest_distance(table, vertex, total_distance)
                    set_previous_node(table, vertex, current_node)
            
            # Mark current node as visited
            visited_nodes.append(current_node)
            print(visited_nodes)  # Debug print to track progress

            # Stop if all nodes have been visited
            if len(visited_nodes) == len(table.keys()):
                break

            # Pick the next node to process
            current_node = get_next_node(table, visited_nodes)

    return table  # Final shortest path table

# Run the algorithm from node 'A'
shortest_path_table = find_shortest_path(graph, table, 'A')

```

### Linked Lists

**linked lists**

It is a data structure in which data elements are stored in a linear order. They provide efficient storage in linear order through pointer-based structures. Pointers are used to store the memory addresses of data items.

**arrays**

It is a data structure in which data elements are stored in a linear order. They provide efficient storage in linear order through pointer-based structures. Pointers are used to store the memory addresses of data items. An array is a collection of data items of the same type, while a linked list is a collection of the same data types stored sequentially and connected by pointers. In lists, data elements are stored in different locations in memory, while in arrays, the elements are stored in contiguous locations in memory. The term base address refers to the address of the location in memory where the first element is stored, and offset refers to an integer that indicates the offset between the first element and a specific element.

**linked lists**

<img width="559" height="146" alt="linked_list" src="https://github.com/user-attachments/assets/10ab1781-b78d-4433-be9f-7090ceee160e" />

A node is an essential component of various data structures, such as linked lists. It is a data container and has one or more links that lead to other nodes, where a link is a pointer.

**singly linked lists**

<img width="711" height="189" alt="singly_linked_list" src="https://github.com/user-attachments/assets/09838cbb-f3c0-4e10-a137-90b9bcfd48aa" />

```python
n1 = Node('eggs')
n1 = Node('ham')
n1 = Node('spam')

n1.next = n2
n2.next = n3

current = n1

while current:
    print(current.data)
    current = current.next

def iter(self):
    current = self.head
    while current:
        val = current.data
        current = current.next
        yield val

```

**append**

**head no tail**

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class SinglyLinkedList:
    '''
    iter all the linked list to append
    '''
    def __init__(self):
        self.head = None
        self.size = 0

    def append(self, data):
        node = Node(data)
        if self.head is None:
            self.head = node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = node
```

**head & tail**

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class SinglyLinkedList:
    '''
    with head and tail
    '''
    def __init__(self):
        self.tail = None
        self.head = None
        self.size = 0

    def append(self, data):
        node = Node(data)
        if self.tail:
            self.tail.next = node
            self.tail = node
        else:
            self.head = node
            self.tail = node
```

<img width="583" height="232" alt="linked_list_append" src="https://github.com/user-attachments/assets/6cf80368-7a0d-4824-89e3-ff201c55a9b9" />

**intermediate positions**

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.tail = None
        self.head = None
        self.size = 0

    def append(self, data):
        node = Node(data)
        if self.tail:
            self.tail.next = node
            self.tail = node
        else:
            self.head = node
            self.tail = node
    
    def append_at_a_location(self, data, index):
        if index < 0:
            print("Invalid index")
            return

        node = Node(data)

        if index == 0:
            node.next = self.head
            self.head = node
            if self.tail is None:
                self.tail = node
            self.size += 1
            return

        current = self.head
        prev = None
        count = 0

        while current:
            if count == index:
                node.next = current
                if prev:
                    prev.next = node
                self.size += 1
                return
            prev = current
            current = current.next
            count += 1

        if count == index:
            if self.tail:
                self.tail.next = node
                self.tail = node
            else:
                self.head = self.tail = node
            self.size += 1
        else:
            print("The list has fewer elements than the index provided.")
```

<img width="955" height="271" alt="linked_list_intermediate_position" src="https://github.com/user-attachments/assets/34e218f0-1cdd-4da3-ad3d-3a53a4d38e76" />

**search**

```python
def iter(self):
        current = self.head
        while current:
            val = current.data
            current = current.next
            yield val
    
    def search(self, data):
        for node in self.iter():
            if data == node:
                return True
        return False
```

**size**

```python
def size(self):
        count = 0
        current = self.head
        while current:
            count += 1
            current = current.next
        return count
```

**delete**

```python
def delete_first_node(self):
        current = self.head
        if self.head is None:
            print('No data element to delete')
        elif current == self.head:
            self.head = current.next

def delete_last_node(self):
        current = self.head
        prev = self.head
        while current:
            if current.next is None:
                prev.next = current.next
                self.size -=1
            prev = current
            current = current.next

def delete(self, data):
        current = self.head
        prev = self.head
        while current:
            if current.data == data:
                if current == self.head:
                    self.head = current.next
                else:
                    prev.next = current.next
                self.size -= 1
                return
            prev = current
            current = current.next
```

<img width="886" height="297" alt="linked_list_delete" src="https://github.com/user-attachments/assets/6605609f-5a7c-45ef-bc30-70de48ea6eae" />

**clear**

```python
def clear(self):
        self.tail = None
        self.head = None
```
**doubly linked list**



### Stacks and Queues

### Trees

### Heaps and Priority Queues

### Hash Tables

### Graphs and Algorithms

### Search

### Sorting

### Selection Algorithms

### String Search Algorithms
