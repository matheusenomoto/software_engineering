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

#### **Basic data types**

The most basic data types are numerical and boolean.

#### **Numerical**

Store numerical values. the whole values, floating point and complexes belong to this type of data.

- **integer (int)**: The interpreter considers a decimal digit sequence as a decimal value, such as integers 43, 10000, or -26
- **float**: Considers a number that has a floating point value as a float type; It is specified with a point
- **complex**: It is represented with the use of floating point values. It contains an orderly pair, a + Ib. Here, A and B represent real numbers and I represents the imaginary component.

#### **Boolean**

This type provides a true or false value and checks if any instruction is true or false.

```sh
True != False
```
#### **Sequence**

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

#### **Complex data types**
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

#### **Python collections module**

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

#### **Introduction to Algorithms**

An algorithm is a sequence of steps that must be followed to complete a specific task/question.

<img width="411" height="127" alt="algorithm" src="https://github.com/user-attachments/assets/5da144ee-bcc1-4b1c-8804-711a4661cdfb" />


#### **Analysis of the unfolding of an algorithm**

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

#### **Asymptotic notation**

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

#### **Algorithm Design Techniques**

It is a powerful tool for visualizing and clearly understanding precisely formulated real-world problems. Brute-force approaches test all possible solution combinations to solve a problem. This approach can provide useful solutions for limited input sizes, but becomes very inefficient as the input size increases. Design technique guidelines also help to easily develop new algorithms for complex problems. There are several algorithm design paradigms.

#### **Recursion**

Calls itself repeatedly to solve the problem until a specific condition is met. Each recursive call generates another recursive call.

* **Base Case**
    * They tell the recursion when it should end, meaning that the recursion will stop when the base condition is met.
* **Recursive Case**
    * The function calls itself recursively and so we move towards the base criteria.

<img width="616" height="340" alt="algorithm_recursive_case" src="https://github.com/user-attachments/assets/9fceb609-85ab-4a16-bfe4-43b726e7e93a" />

#### **Divide and Conquer**

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

#### **Dynamic Programming**

It's the most powerful design technique for solving optimization problems. These problems typically have many possible solutions. It's based on the intuition of the divide-and-conquer technique. Dynamic programming problems have two important characteristics.

* **optimal substructure**
    * Given a problem, if the solution can be obtained by combining the solutions of its subproblems, the problem is said to have an optimal substructure. For example, the i-th Fibonacci number in its seriescan be calculated from the i-th -1 and the i-th -2.
* **overlapping subproblems**
    * When an algorithm needs to repeatedly solve the same subproblem, this happens because the problem has overlapping subproblems.

#### **Greedy Algorithms**

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

#### **linked lists**

It is a data structure in which data elements are stored in a linear order. They provide efficient storage in linear order through pointer-based structures. Pointers are used to store the memory addresses of data items.

#### **arrays**

It is a data structure in which data elements are stored in a linear order. They provide efficient storage in linear order through pointer-based structures. Pointers are used to store the memory addresses of data items. An array is a collection of data items of the same type, while a linked list is a collection of the same data types stored sequentially and connected by pointers. In lists, data elements are stored in different locations in memory, while in arrays, the elements are stored in contiguous locations in memory. The term base address refers to the address of the location in memory where the first element is stored, and offset refers to an integer that indicates the offset between the first element and a specific element.

#### **linked lists**

<img width="559" height="146" alt="linked_list" src="https://github.com/user-attachments/assets/10ab1781-b78d-4433-be9f-7090ceee160e" />

A node is an essential component of various data structures, such as linked lists. It is a data container and has one or more links that lead to other nodes, where a link is a pointer.

#### **singly linked lists**

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

#### **append**

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

#### **head & tail**

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

#### **intermediate positions**

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

#### **search**

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

#### **size**

```python
def size(self):
        count = 0
        current = self.head
        while current:
            count += 1
            current = current.next
        return count
```

#### **delete**

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

#### **clear**

```python
def clear(self):
        self.tail = None
        self.head = None
```
#### **doubly linked list**

The only difference between the doubly linked list and the single linked list is that the doubly linked list also has a pointer pointing to the previous node.

<img width="391" height="163" alt="doubly_linked" src="https://github.com/user-attachments/assets/74378b87-a2db-4431-80b7-51932cf9ef59" />

```python
class Node:
    def __init__(self, data=None, next = None, prev = None):
        self.data = data
        self.next = next
        self.prev = prev

class DoublyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
        self.count = 0
```
#### **append**

```python
    def append_at_start (self, data):
        new_node = Node(data, None, None)
        if self.head is None:
            self.head = new_node
            self.tail = self.head
        else:
            new_node.next = self.head
            self.head.prev = new_node
            self.head = new_node
        self.count += 1

    def append_at_start (self, data):
        new_node = Node(data, None, None)
        if self.head is None:
            self.head = new_node
            self.tail = self.head
        else:
            new_node.next = self.head
            self.head.prev = new_node
            self.head = new_node
        self.count += 1

    def append_at_a_location(self, data, position):
        current = self.head
        while current:
            if current.data == position:
                new_node = Node(data, current, current.prev)
                if current.prev:
                    current.prev.next = new_node
                else:
                    self.head = new_node
                current.prev = new_node
                self.count += 1
                break  # evita múltiplas inserções
            current = current.next
```
<img width="1267" height="364" alt="doubly_linked_append" src="https://github.com/user-attachments/assets/915c5949-5319-4ae8-bd6c-1e55075406ae" />

#### **search**

```python
def iter(self):
        current = self.head
        while current:
            val = current.data
            current = current.next
            yield val
    
    def contains(self, data):
        for node_data in self.iter():
            if data == node_data:
                print(f'Data ({node_data}) item is present in the list')
                return
        print(f'Data ({data}) item is not present in the list')
        return
```

#### **delete**

```python
def delete(self, data):
        current = self.head
        node_deleted = False
        if current is None:
            print("List is empty")
        elif current.data == data:
            # Data at the start
            self.head.prev = None
            node_deleted = True
            self.head = current.next
        elif self.tail.data == data:
            # Data at the end
            self.tail = self.tail.prev
            self.tail.next = None
            node_deleted = True
        else:
            while current:
                # search at intermediate positions
                if current.data == data:
                    current.prev.next = current.next
                    current.next.prev = current.prev
                    node_deleted = True
                current = current.next
            if node_deleted == False:
                print('Item not found')
        
        if node_deleted:
            self.count -=1
```

#### **circular linked lists**

A circular linked list is a variation of a regular linked list where the last node doesn't point to None - instead, it points back to the first node, forming a circle.

**singly circular linked list**

A circular linked list is a variation of a regular linked list where the last node doesn't point to None - instead, it points back to the first node, forming a circle.

<img width="513" height="185" alt="singly_circular_linked_list" src="https://github.com/user-attachments/assets/849dc23b-adcc-44f7-866d-516c8c6a9e46" />

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class SinglyCircularLinkedList:
    def __init__(self):
        self.tail = None
        self.head = None
        self.size = 0

    def append(self, data):
        node = Node(data)
        if self.tail:
            self.tail.next = node
            self.tail = node
            node.next = self.head
        else:
            self.head = node
            self.tail = node
            self.tail.next = self.head 
        self.size +=1

    
    def iter(self):
        if not self.head:
            return
        current = self.head
        while True:
            yield current.data
            current = current.next
            if current == self.head:
                break
    
    def delete(self, data):
        if not self.head:
            return

        current = self.head
        prev = self.tail

        while True:
            if current.data == data:
                if current == self.head:
                    self.head = current.next
                    self.tail.next = self.head
                    if current == self.tail:
                        # Only one node
                        self.head = self.tail = None
                elif current == self.tail:
                    prev.next = self.head
                    self.tail = prev
                else:
                    prev.next = current.next

                self.size -= 1
                return

            prev = current
            current = current.next

            if current == self.head:
                break  # We've looped once; data not found
```

#### **doubly circular linked list**

Each node has next and prev pointers, and the first and last nodes are connected in both directions.

<img width="414" height="212" alt="doubly_circular_linked_list" src="https://github.com/user-attachments/assets/6a7b513c-c346-4e9a-ab27-3893e59e6d34" />

**Applications**

Singly linked lists can be used to represent sparse matrices by storing only nonzero elements along with their indices. They are also useful for representing and manipulating polynomials, where each node stores a term (typically including a coefficient and exponent). Additionally, singly linked lists can serve as a foundation for dynamic memory management schemes, allowing memory to be allocated and deallocated during runtime.

Doubly linked lists are employed by operating systems—for example, in the thread scheduler—to maintain a list of currently active processes. They are also frequently used to implement MRU (Most Recently Used) and LRU (Least Recently Used) caches within the operating system.

Circular linked lists are ideal for implementing round-robin scheduling mechanisms in operating systems. They can also be used to facilitate features such as software undo functionality and to maintain browser histories, enabling features like the back button.

### Stacks and Queues

#### **Stacks**

Stacks are a data structure that stores data in a specific order, similar to arrays and linked lists, but with additional restrictions.
* Data elements can only be inserted at the top of the stack (push operation).
* Data elements can only be deleted from the top of the stack (pop operation).
* Only the last data element can be read from the top of stack (peek operation).

A stack is a LIFO (last in, first out) structure

<img width="836" height="361" alt="stacks" src="https://github.com/user-attachments/assets/d1388ab3-6073-446d-b25e-956b0d3fe374" />

#### **Stack using linked lists**

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class Stack:
    def __init__(self, data=None):
        self.top = None
        self.size = 0
    
    def push(self, data):
        # New node
        node = Node(data)
        if self.top:
            node.next = self.top
            self.top = node
        else:
            self.top = node
        self.size += 1

    def pop(self):
        if self.top:
            data = self.top.data
            self.size -= 1
            if self.top.next:
                self.top = self.top.next
            else:
                self.top = None
            return data
        else:
            print('Stack is empty')
    
    def peek(self):
        if self.top:
            return self.top.data
        else:
            print('Stack is empty')
```

<img width="879" height="195" alt="stack_using_linked_lists" src="https://github.com/user-attachments/assets/3c71dc16-473c-4bf9-b7dc-a9bd751d6c9f" />

#### **Application**

It's used in expression evaluation and conversion (e.g., infix to postfix), syntax parsing (e.g., matching parentheses or HTML tags), and managing function calls through the call stack. Stacks support undo/redo functionality in text editors, enable backtracking in algorithms like maze solving or Sudoku, and handle navigation history in browsers. They are also essential in depth-first search (DFS), memory management (stack frames for local variables), and are used in virtual machines like the JVM for executing bytecode.

#### **Queues**

A queue is a list of elements stored in sequence, with the following restrictions:

* Elements can only be inserted at one end - the back (or tail) of the queue.
* Elements can only be removed from the opposite end - the front (or head) of the queue.
* Only the element at the front of the queue can be read (peek operation)."

A queue is a FIFO (first in, first out) structure

<img width="693" height="155" alt="queues" src="https://github.com/user-attachments/assets/15d708cc-8951-42f6-99a9-2153a7d2ed1a" />

<img width="1042" height="268" alt="queues" src="https://github.com/user-attachments/assets/04f212d9-6cd5-48e6-b5c3-b50462c44a63" />

#### **Queues using lists of python**

```python
class ListQueue:
    def __init__(self):
        self.items = []
        self.front = self.rear = 0
        self.size = 3 # maximum queue size

    def enqueue(self, data):
        if self.size == self.rear:
            print('\n Queue is full')
        else:
            self.items.append(data)
            self.rear += 1 
    def dequeue(self):
        if self.front == self.rear:
            print('\n Queue is empty')
        else:
            data = self.items.pop(0)
            self.rear -= 1
            return data

def test_list_queue():
    q = ListQueue()

    # Test enqueue until full
    q.enqueue(10)
    q.enqueue(20)
    q.enqueue(30)
    print("Queue after 3 enqueues:", q.items)  # Expected: [10, 20, 30]

    # Try enqueueing when full
    q.enqueue(40)  # Expected: "Queue is full"

    # Test dequeue
    print("Dequeued:", q.dequeue())  # Expected: 10
    print("Queue after one dequeue:", q.items)  # Expected: [20, 30]

    # Dequeue remaining elements
    q.dequeue()
    q.dequeue()

    # Try dequeueing when empty
    q.dequeue()  # Expected: "Queue is empty"

test_list_queue()
```

```sh
Queue after 3 enqueues: [10, 20, 30]

 Queue is full
Dequeued: 10
Queue after one dequeue: [20, 30]

 Queue is empty
```

#### **Queues using linked lists**

```python
class Node(object):
    def __init__(self, data=None, next=None, prev=None):
        self.data = data
        self.next = next
        self.prev = prev
    

class LinkedListQueue:
    def __init__(self):
        self.head = None
        self.tail = None
        self.count = 0

    def enqueue(self, data):
        new_node = Node(data, None, None)
        if self.head == None:
            self.head = new_node
            self.tail = self.head
        else:
            new_node.prev = self.tail
            self.tail.next = new_node
            self.tail = new_node
        
        self.count += 1
 
    def dequeue(self):
        if self.count == 0:
            print('Queue is empty.')
            return

        if self.count == 1:
            self.head = None
            self.tail = None
        else:
            self.head = self.head.next
            self.head.prev = None

        self.count -= 1

def test_linked_list_queue():
    q = LinkedListQueue()

    # Enqueue elements
    q.enqueue(10)
    q.enqueue(20)
    q.enqueue(30)

    # Traverse and print queue
    current = q.head
    result = []
    while current:
        result.append(current.data)
        current = current.next
    print("Queue after 3 enqueues:", result)  # Expected: [10, 20, 30]

    # Dequeue 1 element
    q.dequeue()
    current = q.head
    result = []
    while current:
        result.append(current.data)
        current = current.next
    print("Queue after 1 dequeue:", result)  # Expected: [20, 30]

    # Dequeue 2 more to empty it
    q.dequeue()
    q.dequeue()

    # Try dequeue on empty queue
    q.dequeue()  # Expected: 'Queue is empty.'

test_linked_list_queue()
```

```sh
Queue after 3 enqueues: [10, 20, 30]
Queue after 1 dequeue: [20, 30]
Queue is empty.
```

#### **Application**

It can be used to queue individual printouts arriving from each computer on a network to a printer. Operating systems can queue processes to be executed by the CPU. 


### Trees

A tree is a way to organize data in a hierarchical structure. It starts from one top node (point) and branches out.

<img width="698" height="454" alt="trees" src="https://github.com/user-attachments/assets/93a8418f-6781-4d01-80f3-002f1e36f3c5" />

#### Terminologies

* **node**: A node is a single point in the tree that holds data. Every item in the tree is a node.
* **root node**: The root node is the very first or top node in the tree. Everything else comes from it.
* **subtree**: A subtree is any smaller part of the tree that looks like its own tree, starting from a node.
* **simblings**: Siblings are nodes that share the same parent node.
* **leaf node**: A leaf node is a node with no children - it's at the end of a branch.
* **edge**: An edge is a connection between two nodes (like a line between parent and child).
* **parent**: A parent node is one that has one or more children.
* **child**: A child node is one that comes from another node (its parent).
* **level**: The level of a node shows how far it is from the root:
    * Root is at level 0
    * Its children are at level 1
    * And so on...
* **height**: The height of a tree is the number of levels from the root down to the deepest leaf node.
* **depth**: The depth of a node is how far it is from the root (how many edges you go down to reach it).

<img width="982" height="591" alt="tree_terminologies" src="https://github.com/user-attachments/assets/df4a5e92-abbf-460f-9320-43412a2b45db" />

#### binary tree

A binary tree is a special kind of tree where each node has at most two children. These children are often called:

* Left child
* Right child

<img width="587" height="187" alt="binary_tree" src="https://github.com/user-attachments/assets/542697a0-3558-4e59-8ed5-db0151660663" />

#### full binary tree

Every node has either 0 or 2 children. No node has only 1 child.

<img width="273" height="275" alt="full_binary_tree" src="https://github.com/user-attachments/assets/16161f38-10b4-4c8f-91a2-55ab9ed6b5d7" />

#### perfect binary tree

All internal nodes have 2 children and all leaves are at the same level.

<img width="283" height="200" alt="perfect_binary_tree" src="https://github.com/user-attachments/assets/5da4f57b-d726-473a-aa1a-ab4e8a004e9a" />


#### complete binary tree

All levels are fully filled except possibly the last. Last level is filled left to right.

<img width="307" height="279" alt="complete_binary_tree" src="https://github.com/user-attachments/assets/5c5b56f4-4f76-4d31-891b-26ba2f2b14e1" />

#### balanced binary tree

The height difference between left and right subtrees of any node is at most 1. Keeps operations fast (like search).

<img width="243" height="200" alt="balanced_binary_tree" src="https://github.com/user-attachments/assets/d3061789-9b9b-4365-a6ec-c8c9070d79a8" />

#### unbalanced binary tree

One side is much deeper than the other. The tree becomes “tall and skinny” → slower operations (like a linked list).

<img width="243" height="272" alt="unbalanced_binary_tree" src="https://github.com/user-attachments/assets/b9a1615e-dd6b-48ad-bc02-b7c40b37cec3" />

#### Rules

| Type |  Rule |
|:---:|:---:|
| Full | 0 or 2 children only |
| Perfect | Full and all leaves on same level |
| Complete | All levels full except maybe last (filled left to right) |
| Balanced | Heights of subtrees differ by no more than 1 |
| Unbalanced | One or more subtrees are much taller than others |

#### traversals

There are several ways to process and traverse the tree according to the sequence of visiting the root node, the left subtree or the right subtree. There are two main approaches. In the first, we start at a node, traverse each available child node, and continue traversing the next sibling. There are three possible variations of this method: in-order, pre-order, and post-order. Another approach to traversing the tree is to start at the root node, visit all the nodes at each level, and process the nodes level by level.

<img width="320" height="269" alt="traversals" src="https://github.com/user-attachments/assets/a743e448-3a7c-4314-b46b-56aab7d95098" />


```python
class Node:
    def __init__(self, data):
        self.data = data
        self.right_child = None
        self.left_child = None

A = Node('A')
B = Node('B')
C = Node('C')
D = Node('D')
E = Node('E')
F = Node('F')
G = Node('G')
H = Node('H')

A.left_child = B
A.right_child = C

B.left_child = D
B.right_child = E

D.left_child = G
D.right_child = H

C.left_child = F
```

#### in-order

We start by traversing the left subtree recursively, and once the left subtree is visited, the root node is visited, and finally the right subtree is visited recursively.

<img width="555" height="291" alt="in-order" src="https://github.com/user-attachments/assets/37b4d086-1969-49fb-bc0b-5429910f5d88" />

```python
def inorder(root_node):
    current = root_node
    if current is None:
        return
    inorder(current.left_child)
    print(current.data)
    inorder(current.right_child)
```

```sh
G-D-H-B-E-A-F-C
```

#### pre-order

We start by traversing the root node, left subtree, and right subtree.

<img width="554" height="296" alt="pre-order" src="https://github.com/user-attachments/assets/fcc285c7-f6d7-4657-8f17-04625ce759cb" />

```python
def preorder(root_node):
    current = root_node
    if current is None:
        return
    print(current.data)
    preorder(current.left_child)
    preorder(current.right_child)
```

```sh
G-H-D-E-B-F-C-A
```

#### pos-order

We start by traversing the left subtree, right subtree and root node.

<img width="554" height="318" alt="pos_order" src="https://github.com/user-attachments/assets/03190b41-b44d-48f9-857f-4719ebec89c7" />


```python
def posorder(root_node):
    current = root_node
    if current is None:
        return
    posorder(current.left_child)
    posorder(current.right_child)
    print(current.data)
```

```sh
G-H-D-E-B-F-C-A
```

#### level-order

We start by visiting the root of the tree before visiting each node at the next level. We then move on to the next level of the tree, and so on.

<img width="598" height="315" alt="level-order" src="https://github.com/user-attachments/assets/d0d1762a-2af9-4dad-b41b-41f9cee7d937" />


```python
def level_order_traversal(root_node):
    list_of_nodes = []
    traversal_queue = deque([root_node])
    while len(traversal_queue) > 0:
        node = traversal_queue.popleft()
        list_of_nodes.append(node.data)
        if node.left_child:
            traversal_queue.append(node.left_child)
            if node.right_child:
                traversal_queue.append(node.right_child)
    return list_of_nodes
```

```sh
A-B-C-D-E-F-G-H
```

#### expression tree

An expression tree is a binary tree used to represent and evaluate mathematical expressions. Each node in the tree corresponds to an element of the expression - either an operator (like +, *, /, -) or an operand (like numbers or variables).

Structure:

* Leaf nodes: These are the operands (constants or variables).
* Internal nodes: These are the operators (e.g., +, -, *, /).

**infix**: Traversing an expression tree in-order produces infix notation.

<img width="364" height="130" alt="infix" src="https://github.com/user-attachments/assets/8a606c9f-6044-4fd0-9b6d-eec439055539" />
  
**prefix**: Traversing an expression tree pre-order produces prefix notation. Prefix notation is often called Polish notation. In this notation, the operator comes before its operands. For example, the arithmetic expression that adds two numbers would be + 3 4.

<img width="859" height="207" alt="prefix" src="https://github.com/user-attachments/assets/c80cbfe5-bafc-4eab-895c-bb7d969d8332" />

**postfix**: Traversing an expression tree post-order produces postfix notation. Postfix notation, or RPN (reverse Polish notation), inserts the operator after its operands, as in 3 4 +.

<img width="466" height="201" alt="postfix" src="https://github.com/user-attachments/assets/1a9216b3-04b8-457e-a1d9-d700bf50d5d5" />

#### Parsing a reverse Polish expression

To create an expression tree from postfix notation, a stack is used. We process one symbol at a time. If the symbol is an operand, its reference is pushed onto the stack. If the symbol is an operator, we pop two operands from the stack and form a new subtree where the operator is the root and the operands are its children. This new subtree is then pushed back onto the stack.

<img width="514" height="196" alt="parsing_a_reverse_polish_expression_01" src="https://github.com/user-attachments/assets/86dcd6ee-45a5-4b02-91b4-cf502b8662da" />

First, we push operands 4 and 5 onto the stack. When the next symbol, +, is read, it becomes the root of a subtree. We remove two references from the stack: the first value removed will be the right child of the + operator, and the second value will be the left child. We then push this subtree back onto the stack.

<img width="536" height="275" alt="parsing_a_reverse_polish_expression_02" src="https://github.com/user-attachments/assets/bfeae0e8-04db-4e85-ba68-cc87ed629c4d" />

<img width="612" height="292" alt="parsing_a_reverse_polish_expression_03" src="https://github.com/user-attachments/assets/6e7d4b6d-51bc-4092-a068-4947609edb13" />

```python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.right = None
        self.left = None

class Stack:
    def __init__(self):
        self.elements = []
    
    def push(self, item):
        self.elements.append(item)
    
    def pop(self):
        return self.elements.pop()

def calc(node):
    if node.data == "+":
        return calc(node.left) + calc(node.right)
    elif node.data == "-":
        return calc(node.left) - calc(node.right)
    elif node.data == "*":
        return calc(node.left) * calc(node.right)
    elif node.data == "/":
        return calc(node.left) / calc(node.right)
    else:
        return node.data

def test_build_expression_tree_v1():
    expression = '4 5 + 5 3 - *'.split()
    stack = Stack()

    for term in expression:
        if term in '+-*/':
            node = TreeNode(term)
            node.right = stack.pop()
            node.left = stack.pop()
        else:
            node = TreeNode(int(term))
        
        stack.push(node)
    root = stack.pop()
    result = calc(root)
    print(result)

test_build_expression_tree_v1()
```

Expression trees are important because they represent mathematical or logical expressions in a structured, hierarchical way, enabling various powerful operations that are crucial in computing, especially in:

1. Compilers and Interpreters
* Why? Compilers use expression trees to parse and evaluate code
* Example: a + b * c becomes a tree where * is evaluated before + due to tree structure (not just operator precedence rules).
* This structure helps in code generation, optimization, and type checking.

2. Expression Evaluation
Trees can be evaluated recursively, mimicking human-like evaluation. You can easily:

* Evaluate it left-to-right or post-order (for postfix)
* Convert between infix, prefix, and postfix forms
* Handle complex, nested expressions naturally

3. Algebraic Simplification and Optimization

Expression trees let you apply transformations:

* Simplify expressions (a * 1 → a)
* Apply constant folding (3 + 4 → 7)
* Rearrange for performance or accuracy

4. Symbolic Computation

* Tools like Mathematica or SymPy use expression trees to manipulate math symbolically (not numerically).
* Example: differentiate, integrate, expand expressions.

5. Reverse Conversion and Traversals

Convert postfix ↔ infix ↔ prefix using tree traversals:

* In-order → infix
* Pre-order → prefix
* Post-order → postfix

6. Foundation for Abstract Syntax Trees (ASTs)

Expression trees are a subset of ASTs, which are used broadly in:

* Code analysis
* Linters
* Formatters
* Static analyzers

In Short:

Expression trees bridge the gap between raw symbols and structured logic, making them critical for evaluation, optimization, compilation, and symbolic manipulation.

#### binary search tree BST

Binary search tree is a special type of binary tree. It is one of the most important data structure and most common used in computer science applications. It allows fast operations to search, insert, and delete.

A binary tree is called a binary search tree when the value of any node in the tree is greater than the values of all the nodes in its left subtree and less than or equal to all the nodes in its right subtree.

<img width="246" height="196" alt="binary_search_tree_01" src="https://github.com/user-attachments/assets/a9af2870-78c0-46d9-bbc3-fc9fb26e17ae" />

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.right_child = None
        self.left_child = None
    
class Tree:
    def __init__(self):
        self.root_node = None

    def insert(self, data):
        node = Node(data)
        if self.root_node is None:
            self.root_node = node
            return self.root_node
        else:
            current = self.root_node
            parent = None
            while True:
                parent = current
                if node.data < parent.data:
                    current = current.left_child
                    if current is None:
                        parent.left_child = node
                        return self.root_node
                    current = current.right_child
                    if current is None:
                        parent.right_child = node
                        return self.root_node
    
    def inorder(self, root_node):
        current = root_node
        if current is None:
            return
        self.inorder(current.left_child)
        print(current.data)
        self.inorder(current.right_child)
    
    def search(self, data):
        current = self.root_node
        while True:
            if current is None:
                print('Item not found')
                return None
            elif current.data is data:
                print('Found:', data)
                return data
            elif current.data > data:
                current = current.left_child
            else:
                current = current.right_child

def bst_test():
    tree = Tree()
    r = tree.insert(5)
    r = tree.insert(2)
    r = tree.insert(3)
    r = tree.insert(7)
    r = tree.insert(9)
    r = tree.insert(1)
    print('in-order test')
    tree.inorder(r)
    print('root node')
    print('root: ', tree.root_node.data)
    print('searching 9 ...')
    tree.search(9)
    print('searching 13 ...')
    tree.search(13)

bst_test()
```

<img width="265" height="298" alt="binary_search_tree_02" src="https://github.com/user-attachments/assets/b29d04be-61af-4046-92c1-4294d463a707" />

#### Exclusion of nodes

There are three possible scenarios we'll need to handle during this process.

* **No children**: If there are no leaves, we'll remove the node directly from its parent.
* **Having one child**: In this case, we'll swap the value of this node with that of its child and delete it.
* **Having two children**: In this case, we'll first find the successor or predecessor in the in-order scan, swap their values, and delete that node.

<img width="198" height="371" alt="no_children" src="https://github.com/user-attachments/assets/171d8859-6448-4ee4-af7a-2aa3b82c8ae4" />
<img width="187" height="375" alt="having_one_child" src="https://github.com/user-attachments/assets/5dacde90-2029-4d43-9e7f-cdde3fd1a5ef" />
<img width="466" height="329" alt="having_two_children" src="https://github.com/user-attachments/assets/265e0aef-cc5d-4b4e-8d29-59c928b804c0" />

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.right_child = None
        self.left_child = None
    
class Tree:
    def __init__(self):
        self.root_node = None

    def insert(self, data):
        node = Node(data)
        if self.root_node is None:
            self.root_node = node
            return self.root_node
        else:
            current = self.root_node
            while True:
                if data < current.data:
                    if current.left_child is None:
                        current.left_child = node
                        return self.root_node
                    current = current.left_child
                else:
                    if current.right_child is None:
                        current.right_child = node
                        return self.root_node
                    current = current.right_child
    
    def inorder(self, root_node):
        current = root_node
        if current is None:
            return
        self.inorder(current.left_child)
        print(current.data)
        self.inorder(current.right_child)
 
    def search(self, data):
        current = self.root_node
        while True:
            if current is None:
                print('Item not found')
                return None
            elif current.data is data:
                print('Found:', data)
                return data
            elif current.data > data:
                current = current.left_child
            else:
                current = current.right_child
    
    def get_node_with_parent(self, data):
        parent = None
        current = self.root_node

        while current:
            if current.data == data:
                return (parent, current)
            elif current.data > data:
                parent = current
                current = current.left_child
            else:
                parent = current
                current = current.right_child

        return (parent, None)


    def remove(self, data):
        parent, node = self.get_node_with_parent(data)

        if node is None:
            return False

        if node.left_child and node.right_child:
            children_count = 2
        elif node.left_child or node.right_child:
            children_count = 1
        else:
            children_count = 0

        if children_count == 0:
            if parent:
                if parent.left_child == node:
                    parent.left_child = None
                else:
                    parent.right_child = None
            else:
                self.root_node = None

        elif children_count == 1:
            child = node.left_child if node.left_child else node.right_child
            if parent:
                if parent.left_child == node:
                    parent.left_child = child
                else:
                    parent.right_child = child
            else:
                self.root_node = child

        else:
            successor_parent = node
            successor = node.right_child
            while successor.left_child:
                successor_parent = successor
                successor = successor.left_child

            node.data = successor.data

            if successor_parent.left_child == successor:
                successor_parent.left_child = successor.right_child
            else:
                successor_parent.right_child = successor.right_child

        return True


    def print_tree(self, node=None, level=0):
        if node is None:
            node = self.root_node

        if node.right_child:
            self.print_tree(node.right_child, level + 1)

        print('    ' * level + f'-> {node.data}')

        if node.left_child:
            self.print_tree(node.left_child, level + 1)
    
    def find_min(self):
        current = self.root_node
        while current.left_child:
            current = current.left_child
        
        return current.data
    
    def find_max(self):
        current = self.root_node
        while current.right_child:
            current = current.right_child
        
        return current.data
```

```python
def bst_test():
    tree = Tree()
    r = tree.insert(5)
    r = tree.insert(2)
    r = tree.insert(3)
    r = tree.insert(7)
    r = tree.insert(9)
    r = tree.insert(1)
    print('tree')
    tree.print_tree()
    print('in-order test')
    tree.inorder(r)
    print('root node')
    print('root: ', tree.root_node.data)
    print('searching 9 ...')
    tree.search(9)
    print('searching 13 ...')
    tree.search(13)
    print(f'min: {tree.find_min()}')
    print(f'max: {tree.find_max()}')

bst_test()
```

```sh
$ python3 bst.py

tree
        -> 9
    -> 7
-> 5
        -> 3
    -> 2
        -> 1
in-order test
1
2
3
5
7
9
root node
root:  5
searching 9 ...
Found: 9
searching 13 ...
Item not found
min: 1
max: 9
```

### Heaps and Priority Queues

A heap data structure is a tree-based structure in which each node in the tree has a specific relationship with other nodes, and they are stored in a predefined order.

A priority queue is an important data structure, similar to queue and stack data structures, that stores data with a priority associated with it.

#### heaps

Heaps can be of two types, max heaps and min heaps. In a max heap, the value of each parent node must always be greater than or equal to that of all its children. In a min heap, the value of each parent node must always be less than or equal to that of all its children.

<img width="654" height="325" alt="max_and_mean_heap" src="https://github.com/user-attachments/assets/47f2f8bb-3435-4da6-8dc3-530b1399d08f" />

#### insert

Inserting an item into a min-heap occurs in two steps. First, we add the new element to the end of the list and increase the heap size by one. Second, after each insertion operation, we must fit the new element somewhere up the tree to organize all the nodes in a way that meets the heap property.


<img width="1085" height="218" alt="heap_insert" src="https://github.com/user-attachments/assets/17fe95fd-c062-45ab-aefa-bf300f6b9088" />

#### delete

When we delete the root node, we'll need a new root node. We'll then take the last item in the list and make it the new root. Since the last node selected may not be the lowest valued element, we will need to rearrange the heap nodes. We'll rearrange the nodes from the root node to the last node. This process is called heapfication. Since we'll be moving from top to bottom in the heap, the process
is called percolate down.


<img width="1150" height="202" alt="heap_delete_root" src="https://github.com/user-attachments/assets/06617bcd-a463-482d-8447-df23f49b75e0" />

<img width="1217" height="290" alt="heap_delete_at_location" src="https://github.com/user-attachments/assets/e9cae815-fd9c-4632-8bb5-e888893683ec" />

```python
class MinHeap:
    def __init__(self):
        self.heap = [0]  # Dummy element at index 0
        self.size = 0

    def arrange(self, k):  # aka bubble_up
        while k // 2 > 0:
            if self.heap[k] < self.heap[k // 2]:
                self.heap[k], self.heap[k // 2] = self.heap[k // 2], self.heap[k]
            k //= 2
    
    def insert(self, item):
        self.heap.append(item)
        self.size += 1
        self.arrange(self.size)
    
    def minchild(self, k):
        if k * 2 + 1 > self.size:
            return k * 2
        elif self.heap[k * 2] < self.heap[k * 2 + 1]:
            return k * 2
        else:
            return k * 2 + 1
    
    def sink(self, k):  # aka bubble_down
        while k * 2 <= self.size:
            mc = self.minchild(k)
            if self.heap[k] > self.heap[mc]:
                self.heap[k], self.heap[mc] = self.heap[mc], self.heap[k]
            k = mc
    
    def delete_at_root(self):
        item = self.heap[1]
        self.heap[1] = self.heap[self.size]
        self.size -= 1
        self.heap.pop()
        self.sink(1)
        return item
    
    def delete_at_location(self, k):
        if k > self.size or k <= 0:
            raise IndexError("Index out of bounds")
        
        removed_item = self.heap[k]
        self.heap[k] = self.heap[self.size]
        self.size -= 1
        self.heap.pop()
        
        if k <= self.size:
            if k > 1 and self.heap[k] < self.heap[k // 2]:
                self.arrange(k)  # Bubble up
            else:
                self.sink(k)     # Bubble down
        
        return removed_item
```

#### priority queue

A priority queue is a queue-like data structure in which data is retrieved according to the FIFO (First In, First Out) policy, but in the priority queue, a priority is associated with the data.

<img width="466" height="186" alt="priority_queue" src="https://github.com/user-attachments/assets/5787a900-0456-46a4-a4ec-8b5b3c98932d" />

```python
class Node:
    def __init__(self, info, priority):
        self.info = info
        self.priority = priority

class PriorityQueue:
    def __init__(self):
        self.queue = []

    def insert(self, node):
        for i in range(len(self.queue)):
            if node.priority < self.queue[i].priority:
                self.queue.insert(i, node)
                return
        self.queue.append(node)

    def delete(self):
        if not self.queue:
            return None
        return self.queue.pop(0)

    def show(self):
        for node in self.queue:
            print(f'{node.info} - {node.priority}')
```

```python
class PriorityQueueHeap:
    def __init__(self):
        self.heap = [()]
        self.size = 0
    
    def arrange(self, k):
        while k // 2 > 0:
            if self.heap[k][0] < self.heap[k//2][0]:
                self.heap[k], self.heap[k//2] = self.heap[k//2], self.heap[k]
            k //= 2
    
    def insert(self, priority,item):
        self.heap.append((priority, item))
        self.size += 1
        self.arrange(self.size)

    def sink(self, k):
        while k * 2 <= self.size:
            mc = self.minchild(k)
            if self.heap[k][0] > self.heap[mc][0]:
                self.heap[k], self.heap[mc] = self.heap[mc], self.heap[k]
            k = mc
    
    def minchild(self, k):
        if k * 2 +1 > self.size:
            return k * 2 
        elif self.heap[k*2][0] < self.heap[k*2+1][0]:
            return k * 2
        else:
            return k * 2 + 1
    
    def delete_at_root(self):
        item = self.heap[1][1]
        self.heap[1] = self.heap[self.size]
        self.size -= 1
        self.heap.pop()
        self.sink(1)
        return item
```

Of course! Here are an introduction, an applications section, and a conclusion for your article on heaps and priority queues.

***

#### Applications of Heaps and Priority Queues

The efficiency of heaps in implementing priority queues makes them essential tools for solving a wide variety of computational problems. Their ability to quickly access the element with the highest (or lowest) priority is crucial in many algorithms. Here are some key applications:

*   **Graph Algorithms:** Heaps are central to famous algorithms like **Dijkstra's** for finding the shortest path and **Prim's** for finding a Minimum Spanning Tree (MST). In these cases, a min-priority queue is used to efficiently track which vertex to visit or which edge to add next based on the lowest cost or distance.
*   **Operating System Schedulers:** CPU process scheduling is a classic priority queue problem. The operating system assigns priorities to different tasks (e.g., system processes vs. user applications). The scheduler uses a priority queue to decide which process to run next, ensuring that critical tasks are executed promptly.
*   **Event-Driven Simulation:** In simulations where events are scheduled to occur at different times, a priority queue can manage the event list. The event with the earliest timestamp has the highest priority. The simulation engine repeatedly processes the next event from the queue, which may in turn add new future events to it.
*   **Data Compression:** The **Huffman coding** algorithm, which creates optimal prefix codes to compress data, uses a min-heap to build its encoding tree. It repeatedly merges the two nodes with the lowest frequencies until a single tree is formed.
*   **Finding the Kth Largest/Smallest Element:** Heaps provide an efficient way to find the k-th smallest or largest element in a collection without sorting the entire list. For example, to find the k-th largest element, you can maintain a min-heap of size *k*. As you iterate through the elements, you add them to the heap, and if the heap's size exceeds *k*, you remove the smallest element. After processing all elements, the root of the heap will be the k-th largest element.

### Hash Tables

It is a data structure that implements an associative array in which data is stored by mapping keys to values as key-value pairs. When we look up an element in the hash table, hashing the key provides the index of the corresponding record in the table.

<img width="702" height="248" alt="hash_table_01" src="https://github.com/user-attachments/assets/ae172cb9-f572-491e-91f2-69a96c00cee7" />

#### intro

It is a data structure that implements an associative array in which data is stored by mapping keys to values as key-value pairs. When we look up an element in the hash table, hashing the key provides the index of the corresponding record in the table.

Dictionaries are a widely used data structure, typically created using a hash table. This model uses the key-value concept instead of using the index to access the value, the key is used.

#### hash function

Hashing is a technique in which, when we feed data of arbitrary size to a function, we obtain a simplified, smaller value. This function is called a hashing function.

In practice, most hash functions are imperfect and generate collisions. Hash functions can provide the same hash value for more than one given piece of data.

```python
value = sum(map(ord, 'hello world'))
print(value)
```
<img width="554" height="104" alt="sum_map_hello_world" src="https://github.com/user-attachments/assets/ef4be1f2-8cef-46f7-b5f3-68f4d92a666d" />

```python
value = sum(map(ord, 'world hello'))
print(value)
```

```python
value = sum(map(ord, 'gello xorld'))
print(value)
```

```sh
enomoto@ubuntu:~$ python3 simple_hash.py 
1116
1116
1116
```
#### perfect hash function

Hash functions allow us to obtain a unique value for a specific string (which can be any data type). The goal is to create a hash function that reduces collisions, is fast, easy to calculate, and distributes data items evenly in the hash table.

The difficulty lies in the tradeoff between the collision-free hash function and the speed that meets the hash table.

<img width="780" height="147" alt="perfect_hash_function_01" src="https://github.com/user-attachments/assets/de71c6b9-cdc1-41d9-bfb7-e96623434f73" />

```python
def myhash(s):
    mult = 1
    hv = 0
    for ch in s:
        hv += mult * ord(ch)
        mult += 1
    
    return hv
```

```sh
hello world  - hashed: 6736
world hello  - hashed: 6616
gello xorld  - hashed: 6742
ad  - hashed: 297
ga  - hashed: 297
```

We still won't have a perfect hash function, since we got the same hash values for these two different strings.

#### Collision Resolution

Typically, each position in a hash table is called a slot or bucket and can store one element. Each data item, in the form of a key-value pair, is stored in the hash table in a position defined by the key's hash value.

<img width="642" height="367" alt="collision_resolution" src="https://github.com/user-attachments/assets/09191f6a-5a7f-4785-a481-e97422c3a2ef" />

One way to resolve this type of collision is to find another empty slot from the collision position. This collision resolution process is called open addressing.

#### open addressing

Key values are stored in the hash table, and collisions are resolved using the probing technique. Collisions are resolved by probing from an alternate position until reaching an unused slot in the hash table for storing the data item.

There are 3 types of probing:

* Linear Probing
* Quadratic Probing
* Double Hashing

#### Linear Probing

Visiting each slot is a linear way to resolve collisions, in which we linearly search for the next available slot by adding 1 to the previous hash value where the collision occurred. This is known as linear probing. We can resolve the conflict by adding 1 to the sum of the ordinal values of each character in the string key, which will be used to calculate the final hash value by its modulo the size of the hash table.

<img width="432" height="229" alt="linear_probing" src="https://github.com/user-attachments/assets/085f340b-cb40-47db-bf58-21d8005c1d6f" />

#### storing elements in a hash table

The put method stores a key–value pair in the hash table by first creating a HashItem and finding its position using the _hash function. If that position is already taken by a different key, it uses linear probing (checking the next slots in order) until it finds either an empty slot or the same key to update. If it finds an empty slot, it increases the count and saves the item there, then checks if the table needs to grow.

#### augment a hash table

To increase the table size, we need to compare the table size and the table count. Typically, the hash table load factor is used to expand the table size; it is defined by the number of used slots (n) divided by the total number (k) of slots in the table.

load factor = n/k

```python
class HashItem:
    def __init__(self, key, value):
        self.key = key
        self.value = value
    
class HashTable:
    def __init__(self, initial_size=10):
        self.size = initial_size
        self.slots = [None for _ in range(self.size)]
        self.count = 0
        self.MAXLOADFACTOR = 0.6  # trigger growth after > 0.6 load factor
    
    def _hash(self, key):
        mult = 1
        hv = 0
        for ch in key:
            hv += mult * ord(ch)
            mult += 1
        return hv % self.size
    
    def put(self, key, value):
        item = HashItem(key, value)
        h = self._hash(key)
        while self.slots[h] is not None:
            if self.slots[h].key == key:
                break
            h = (h + 1) % self.size
        if self.slots[h] is None:
            self.count += 1
        self.slots[h] = item
        self.check_growth()
    
    def check_growth(self):
        load_factor = self.count / self.size
        if load_factor > self.MAXLOADFACTOR:
            print(f"\nLoad factor before growing: {load_factor:.2f}")
            self.growth()
            print(f"Load factor after growing: {self.count / self.size:.2f}")
    
    def growth(self):
        old_slots = self.slots
        old_size = self.size
        self.size = 2 * self.size
        self.slots = [None for _ in range(self.size)]
        self.count = 0
        print(f"\n--- GROWTH from {old_size} to {self.size} slots ---")
        for item in old_slots:
            if item is not None:
                print(f"Rehashing key '{item.key}' from old hash {self._hash_old(item.key, old_size)} to new hash {self._hash(item.key)}")
                self.put(item.key, item.value)

    def _hash_old(self, key, old_size):
        """Helper to compute old hash value for display."""
        mult = 1
        hv = 0
        for ch in key:
            hv += mult * ord(ch)
            mult += 1
        return hv % old_size

    def get(self, key):
        h = self._hash(key)
        while self.slots[h] is not None:
            if self.slots[h].key == key:
                return self.slots[h].value
            h = (h + 1) % self.size
        return None

    def __setitem__(self, key, value):
        self.put(key, value)

    def __getitem__(self, key):
        return self.get(key)

    def display_slots(self):
        for i, v in enumerate(self.slots):
            if v:
                print(f"{i}: {v.key} -> {v.value}")
            else:
                print(f"{i}: None")


# -------- DEMO --------
ht = HashTable(initial_size=10)

# Insert keys until we pass load factor 0.6
for i in range(1, 8):  # 7th insert triggers growth
    ht[f"key{i}"] = i
    print(f"Inserted key{i}, hash (size={ht.size}): {ht._hash(f'key{i}')}")

print("\nSlots after insertion (before growth):")
ht.display_slots()
```

```sh
Inserted key1, hash (size=10): 8
Inserted key2, hash (size=10): 2
Inserted key3, hash (size=10): 6
Inserted key4, hash (size=10): 0
Inserted key5, hash (size=10): 4
Inserted key6, hash (size=10): 8

Load factor before growing: 0.70

--- GROWTH from 10 to 20 slots ---
Rehashing key 'key4' from old hash 0 to new hash 0
Rehashing key 'key2' from old hash 2 to new hash 12
Rehashing key 'key7' from old hash 2 to new hash 12
Rehashing key 'key5' from old hash 4 to new hash 4
Rehashing key 'key3' from old hash 6 to new hash 16
Rehashing key 'key1' from old hash 8 to new hash 8
Rehashing key 'key6' from old hash 8 to new hash 8
Load factor after growing: 0.35
Inserted key7, hash (size=20): 12

Slots after insertion (before growth):
0: key4 -> 4
1: None
2: None
3: None
4: key5 -> 5
5: None
6: None
7: None
8: key1 -> 1
9: key6 -> 6
10: None
11: None
12: key2 -> 2
13: key7 -> 7
14: None
15: None
16: key3 -> 3
17: None
18: None
19: None
```

#### quadratic probing

Also an open addressing scheme for resolving collisions in hash tables. It resolves the collision by calculating the key's hash value and adding successive values of a quadratic polynomial. The new hash is calculated iteratively until an empty slot is found. If a collision occurs, the next free slots are checked at locations h + 1², h + 2², h + 3², and so on.

<img width="599" height="446" alt="quadratic_probing" src="https://github.com/user-attachments/assets/c6631778-1e07-4074-881c-7f8c4baa8909" />

#### double hashing

The double hashing collision resolution technique uses two hash functions. First, the primary function is used to calculate the index position in the hash table, and whenever a collision occurs, we use another hash function to find the next free slot and store the data by incrementing the hash value.

(h¹(key) + i*h²(key)) mod table_size

h¹(key) = key mod table_size

It is important that the second hash function is fast, easy to compute, should not have 0 as a result, and should be different from the first function.

<img width="728" height="481" alt="double_hashing" src="https://github.com/user-attachments/assets/c21f5af1-98a3-4a9c-8547-c6b85a352fce" />

#### separate chaining

In chaining, hash table slots are initialized with empty lists. When a data element is inserted, it is appended to the list that corresponds to its hash value.

<img width="975" height="219" alt="separate_chaining" src="https://github.com/user-attachments/assets/90f1169f-a209-4679-8639-2d15ce86ebcc" />


#### symbol table 

They are used by compilers and interpreters to record the symbols and different entities, such as objects, classes, variables and function names, that have been declared in a program.

### Graphs and Algorithms

Graphs are non-linear data structures in which the problem is represented as a network by connecting a set of nodes as edges.

#### Graphs

A graph is a set with a finite number of vertices (nodes) and edges (links). It is a formal mathematical representation of a network, a graph G is an ordered pair of a set V of vertices and a set E of edges.

<img width="1097" height="560" alt="graphs_01" src="https://github.com/user-attachments/assets/e22a4031-8295-4963-be55-c4af42f9fb5e" />

* **node or vertice**: A point or node in a graph is called a vertice.
* **edge**: It is a connection between two nodes.
* **loop**: When an edge of a node loops back on itself.
* **degree of a vertice/node**: The total number of edges that are incident at a specific node.
* **adjacency**: Refers to the connection(s) existing between two nodes.
* **path**: A sequence of nodes and edges between two nodes represents a path.
* **leaf node**: A vertice is known as a leaf node when it has exactly one degree (one edge)

#### directed and undirected

When the edges of a graph are undirected, the graph is known as an undirected graph, when the edges have directions, it is known as a directed graph.

<img width="955" height="367" alt="graphs_directed_and_undirected" src="https://github.com/user-attachments/assets/3a035c95-427e-42e1-a1f3-612e7c5e7057" />

#### directed acyclic graph DAG

All edges are directed from one node to another, so the sequence of edges never forms a closed loop. A cycle is formed in a graph when the starting node of the first edge is equal to the ending node of the last edge in a sequence.

<img width="270" height="256" alt="directed_acyclic_graph_dag" src="https://github.com/user-attachments/assets/a83afa54-03e7-4c99-957f-5d0fb55b7362" />

In a directed acyclic graph, if we follow any path from a specific node, we will never find a path that ends at the same node.

#### weighted graph

A weighted graph is one that has a numerical weight associated with its edges. It can be directed or undirected.

<img width="336" height="298" alt="weighted_graph" src="https://github.com/user-attachments/assets/fe36242f-a304-4972-bfff-5635b9ce0ac8" />

#### bipartite graph

A bipartite graph (also known as a bigraph) is a special graph in which all nodes can be divided into two sets in such a way that edges connect the nodes of one set to the nodes of the other set.

<img width="407" height="327" alt="bipartite_graph" src="https://github.com/user-attachments/assets/e72296ac-46a2-4375-9047-9a3b26b554e0" />

#### representation of graphs

A graph representation technique is the way we store the graph in memory.

Graphs can be represented using two methods:

1. adjacency list
2. adjacency matrix

An adjacency list representation is based on a linked list. In it, we represent the graph by maintaining a list of neighbors for each vertex in the graph. In an adjacency matrix representation, we maintain a matrix that represents which nodes are adjacent to which others in the graph.

If a 200-node graph has, say, 100 edges, it's best to store this type of graph in an adjacency list, because if we use an adjacency matrix, the matrix size will be 200x200 with many zero values. The adjacency matrix is preferable when the graph is expected to have many edges, and thus the matrix will be dense. In the adjacency matrix, it's much easier to search for and verify the presence or absence of an edge compared to when using an adjacency list representation.

#### adjacency list

A linked list can be used to implement an adjacency list. To represent the graph, we need the number of linked lists to be equal to the total number of nodes in the graph.

<img width="747" height="271" alt="adjacency_list" src="https://github.com/user-attachments/assets/1dfbc0a3-ca18-4d60-8922-0b2942912187" />

```python
adj_list_graph = dict()
adj_list_graph['A'] = ['B','C']
adj_list_graph['B'] = ['E','C','A']
adj_list_graph['C'] = ['A','B','E','f']
adj_list_graph['E'] = ['B','C']
adj_list_graph['F'] = ['C']

print(adj_list_graph)
```

```sh
# {'A': ['B', 'C'], 'B': ['E', 'C', 'A'], 'C': ['A', 'B', 'E', 'f'], 'E': ['B', 'C'], 'F': ['C']}
```

#### adjacency matrix

The graph is represented by displaying nodes and their interconnections through edges. Using this method, the dimensions (V x V) of a matrix are used to represent the graph, and each cell represents an edge. A matrix is a two-dimensional array. Therefore, the idea here is to represent the cells of the matrix with a 1 or a 0 depending on whether or not two nodes are connected by an edge.

<img width="264" height="295" alt="adjacency_matrix" src="https://github.com/user-attachments/assets/121efef2-b91d-4bb5-bb47-843d86453b20" />

|  | A | B | C | E | F |
|:---:|:---:|:---:|:---:|:---:|:---:|
| A | 0 | 1 | 1 | 0 | 0 |
| B | 1 | 0 | 1 | 1 | 0 |
| C | 1 | 1 | 0 | 1 | 1 |
| E | 0 | 1 | 1 | 0 | 0 |
| F | 0 | 0 | 1 | 0 | 0 |

#### graph traversal

A graph traversal means visiting all nodes in the graph while recording which nodes have already been visited and which have not yet been visited. Graph traversal, also known as a graph search algorithm, is very similar to tree scanning algorithms, such as pre-order, in-order, and post-order, and to level-order algorithms, as with them, in a graph search algorithm, we start at a node and traverse the edges until we reach all the other nodes in the graph.

A common graph traversal strategy is to follow a path until an endpoint is reached and then reverse the upward sweep until an alternative path is found. Graph traversal algorithms are important for solving several basic problems. They can be useful for determining how to get from one node to another in a graph and for defining which path from node A to B is better than other paths.

#### breadth-first search

It works very similarly to how a level-by-level in-order traversal algorithm works in a tree structure. It operates level by level, starting by visiting the root node at level 1, and then visiting all nodes in the first level directly connected to the root node. After visiting all nodes at level 1, nodes at level 2 are visited.

A queue data structure is used to store information about the nodes to be visited in a graph.

<img width="1310" height="625" alt="queue_data_structure" src="https://github.com/user-attachments/assets/e17a5bdc-2f72-49fb-b9fa-d8ae3adc843a" />

#### Example

<img width="597" height="400" alt="image" src="https://github.com/user-attachments/assets/bae83a06-4266-4c0e-a1ef-5b93573f9832" />

```python
from collections import deque

graph = dict()
graph['A'] = ['B','G','D']
graph['B'] = ['A','F','E']
graph['C'] = ['F', 'H']
graph['D'] = ['F', 'A']
graph['E'] = ['B', 'G']
graph['F'] = ['B', 'D', 'C']
graph['G'] = ['A', 'E']
graph['H'] = ['C']

print(graph)

def breadth_first_search(graph, root):
    visited_vertices = list()
    graph_queue = deque([root])
    visited_vertices.append(root)

    node = root

    while len(graph_queue) > 0:
        node = graph_queue.popleft()
        adj_nodes = graph[node]

        remaining_elements = set(adj_nodes).difference(set(visited_vertices))
        if len(remaining_elements) > 0:
            for elem in sorted(remaining_elements):
                visited_vertices.append(elem)
                graph_queue.append(elem)
    
    return visited_vertices

print(breadth_first_search(graph, 'A'))
```

```sh
# ['A', 'B', 'D', 'G', 'E', 'F', 'C', 'H']
```

#### depth-first search

Traversing the graph is similar to how the pre-order traversal algorithm works on trees. We traverse the tree to the depth of any given path in the graph. Therefore, child nodes are visited before their sibling nodes.

We start with the root node, visit it first, and then check all adjacent vertices of the current node. We begin by visiting one of the adjacent nodes. If the edge leads to a visited node, we return to the current node. However, if the edge leads to an unvisited node, we go to that node and continue processing from there. We continue with the same process until we reach an endpoint where there are no visited nodes. In this case, we return to the previous nodes and stop when we reach the root node.

```python
graph = dict()
graph['A'] = ['B','S']
graph['B'] = ['A']
graph['S'] = ['A', 'C', 'G']
graph['D'] = ['C']
graph['G'] = ['S', 'F', 'H']
graph['H'] = ['G', 'E']
graph['E'] = ['C', 'H']
graph['F'] = ['C', 'G']
graph['C'] = ['D', 'S', 'E', 'F']

def depth_first_search(graph, root):
    visited_vertices = []
    stack = [root]

    while stack:
        node = stack.pop()
        if node not in visited_vertices:
            visited_vertices.append(node)
            # Push neighbors in reverse order to get correct traversal
            for neighbor in reversed(graph[node]):
                if neighbor not in visited_vertices:
                    stack.append(neighbor)

    return visited_vertices

print(depth_first_search(graph, 'A'))
```

```sh
['A', 'B', 'S', 'C', 'D', 'E', 'H', 'G', 'F']
```

<img width="1064" height="313" alt="depth_first_search_01" src="https://github.com/user-attachments/assets/b7a49f1b-d2c0-47c6-820d-798f238a312f" />
<img width="1064" height="313" alt="depth_first_search_02" src="https://github.com/user-attachments/assets/60992890-62b0-4967-851a-e2e04fd2ace8" />
<img width="1064" height="313" alt="depth_first_search_03" src="https://github.com/user-attachments/assets/358a33e9-afff-4db1-9c58-ce9bad2c4bcf" />
<img width="1064" height="313" alt="depth_first_search_04" src="https://github.com/user-attachments/assets/095c0281-f713-4ddb-a148-8c493a1173b2" />
<img width="1064" height="313" alt="depth_first_search_05" src="https://github.com/user-attachments/assets/b2d27414-3d5d-4fc4-9090-10bfd8c10b59" />
<img width="1064" height="313" alt="depth_first_search_06" src="https://github.com/user-attachments/assets/94f22abf-2413-4cba-8361-8dea0193c89f" />
<img width="1064" height="313" alt="depth_first_search_07" src="https://github.com/user-attachments/assets/2ad5a63c-71b5-4f69-bac9-eb8666cf1f87" />
<img width="1064" height="313" alt="depth_first_search_08" src="https://github.com/user-attachments/assets/6c80e3e1-e275-476d-9366-3e4db0fdf174" />
<img width="1064" height="313" alt="depth_first_search_09" src="https://github.com/user-attachments/assets/84f66576-1ce8-48b2-9e4a-023178bbf0a2" />

```python
graph = dict()
graph['A'] = ['B','S']
graph['B'] = ['A']
graph['S'] = ['A', 'C', 'G']
graph['D'] = ['C']
graph['G'] = ['S', 'F', 'H']
graph['H'] = ['G', 'E']
graph['E'] = ['C', 'H']
graph['F'] = ['C', 'G']
graph['C'] = ['D', 'S', 'E', 'F']

def depth_first_search(graph, root):
    visited_vertices = []
    stack = [root]

    while stack:
        node = stack.pop()
        if node not in visited_vertices:
            visited_vertices.append(node)
            # Push neighbors in reverse order to get correct traversal
            for neighbor in reversed(graph[node]):
                if neighbor not in visited_vertices:
                    stack.append(neighbor)

    return visited_vertices

print(depth_first_search(graph, 'A'))
```

```sh
['A', 'B', 'S', 'C', 'D', 'E', 'H', 'G', 'F']
```

#### minimum spanning tree MST

It is a subset of the edges of a connected graph, containing a weighted edge graph that connects all nodes, with the smallest possible total edge weights and no cycles.

<img width="1008" height="352" alt="minimum_spanning_tree_mst" src="https://github.com/user-attachments/assets/8989cfb1-f593-4bbd-8348-d74e8fa92e3f" />

#### Kruskal's algorithm

Kruskal's algorithm is widely used to search for the spanning tree of a specific weighted, connected, and undirected graph. It is based on the greedy approach, as we search for the lowest-cost edge and add it to the tree, then, in each iteration, we continue adding the lowest-weight edge to the tree.

#### Prim's algorithm

Prim's algorithm also relies on a greedy approach to finding the minimum-cost spanning tree. It's very similar to Dijkstra's algorithm for finding the shortest path in a graph. In this algorithm, we start with an arbitrary node as the starting point and then examine the edges leading from the selected nodes and traverse the one with the lowest cost (or weight).

### Search

An important operation for every data structure is searching for elements in a data collection. Types of search algorithms:

* Linear search algorithm
* Jump search algorithm
* Binary search algorithm
* Interpolation search algorithm
* Exponential search algorithm

#### search intro

A search operation is performed to find the location of the desired data item within a collection of data items. The search algorithm should return the location where the searched value is present.

#### linear search

The simplest approach to searching for an item in a list is to do a linear search, in which case we search for items one by one in the entire list. The linear search approach depends on how the list items are stored in memory.

#### unordered linear search

Unordered linear search is a linear search algorithm in which the given list of data items is unordered.

```python
def linear_search(unordered_list, term):
    for i, item in enumerate(unordered_list):
        if term == unordered_list[i]:
            return i
    return None
```

<img width="207" height="50" alt="unordered_linear_search" src="https://github.com/user-attachments/assets/b4b74a33-f769-4fb6-a3ef-d3116f490799" />

#### ordered linear search

If the data elements are already orphaned in an orderly manner, the linear search algorithm can be improved.
* moves sequentially
* if the value of a search item is greater than the object or item currently being checked in the loop, exit and return None

```python
def linear_search_ordered(ordered_list, term):
    ordered_list_size = len(ordered_list)

    for i in range(ordered_list_size):
        if term == ordered_list[i]:
            return i
        elif ordered_list[i] > term:
            return None
    return None
```

<img width="207" height="50" alt="ordered_linear_search" src="https://github.com/user-attachments/assets/474b89d9-f778-45c1-a707-9bd8ddee524e" />

#### jump search

The Jump Search algorithm is an improvement over Linear Search for finding a specific element in a sorted (ordered) list. It works as follows:

* Divide the list into blocks of size approximately √n.
* Jump through the list by checking the last element of each block:
    * If the search value is greater than the last element of the block, move to the next block.
    * If the search value is less than or equal to the last element of the block, the element (if it exists) must be within this block.
* Apply Linear Search inside the identified block.
* If the search value is equal to the compared element, return its index.

<img width="962" height="241" alt="jump_search" src="https://github.com/user-attachments/assets/dcd1067d-058a-46cb-ad7c-63fb75fa510a" />

```python
def jump_search(ordered_list, item):
    print('Entering Jump Search')
    list_size = len(ordered_list)
    block_size = int(math.sqrt(list_size))  # must be integer
    i = 0
    
    while i < list_size:
        print(f'Block under consideration - {ordered_list[i:i+block_size]}')
        
        # If last element of block is >= item, search inside the block
        if i + block_size >= list_size or ordered_list[i + block_size - 1] >= item:
            block_list = ordered_list[i:min(i + block_size, list_size)]
            j = linear_search_ordered(block_list, item)
            if j is None:
                print('Element not found')
                return None
            return i + j
        
        i += block_size
    
    return None
```
#### binary search

First, it compares the search element with the middle element of the list. If the search element is smaller than the middle element, the half of the list with elements larger than the middle element is discarded. The process is repeated recursively. With each iteration, half of the search space is discarded.

```python
def binary_search(arr, start, end, key):
    while start <= end:
        mid = start + (end - start) // 2
        if arr[mid] == key:
            return mid
        elif arr[mid] < key:
            start = mid + 1
        else:
            end = mid - 1
    return -1
```

<img width="428" height="421" alt="algorithm_binary_search_01" src="https://github.com/user-attachments/assets/91c23d7c-8129-499e-9ebc-51a59f22099c" />

#### interpolation search

The binary search algorithm is efficient at performing searches. It always reduces the search space by half, discarding one of the halves depending on the value of the item being searched. The interpolation algorithm works efficiently when there are elements evenly distributed in the sorted list. In interpolation search, we calculate the starting position of the search depending on the item being searched. The starting position is almost always near the beginning or end of the list; if the search item is near the first element, the starting position should be near the beginning of the list, and if the item is near the end of the list, the starting position should be near the end.

```python
def interpolation_search(ordered_list, item):
    low = 0
    high = len(ordered_list) - 1

    while low <= high and item >= ordered_list[low] and item <= ordered_list[high]:
        # Estimate position using interpolation formula
        if ordered_list[high] == ordered_list[low]:
            if ordered_list[low] == item:
                return low
            else:
                return None

        pos = low + int(
            ((float(high - low) / (ordered_list[high] - ordered_list[low])) * (item - ordered_list[low]))
        )

        # Check the estimated position
        if ordered_list[pos] == item:
            return pos
        elif ordered_list[pos] < item:
            low = pos + 1
        else:
            high = pos - 1

    return None

ordered_list = [44,60,75,100,120,230,250]
print(interpolation_search(ordered_list, 230))   # Expected: 5
```

<img width="854" height="138" alt="interpolation_search" src="https://github.com/user-attachments/assets/648585e3-b5a3-4aea-aeae-c3aac8f0545e" />

#### interpolation concepts

Interpolation is the mathematical procedure applied to derive value between two points having a prescribed value. In simple words, we can describe it as a process of approximating the value of a given function at a given set of discrete points. Hence, one can apply it in estimating varied cost concepts, mathematics, statistics, etc.

<img width="534" height="716" alt="interpolation_math" src="https://github.com/user-attachments/assets/2074adac-2066-44dd-a877-4410ad1f37cb" />

#### exponential search

Exponential search is another search algorithm most commonly used when the number of elements in a list is large. It is also known as galloping search and doubling search. The exponential search algorithm works in two steps:

* Given a sorted array of n data elements, we first determine the subrange in the original list where the desired item may be present.
* Then, we use the binary search algorithm to find the sought-after value within the subrange of elements identified in the previous step.

```python
def binary_search(ordered_list, left, right, item):
    while left <= right:
        mid = left + (right - left) // 2

        if ordered_list[mid] == item:
            return mid
        elif ordered_list[mid] < item:
            left = mid + 1
        else:
            right = mid - 1
    return None

def exponential_search(ordered_list, item):
    if not ordered_list:
        return None

    # Check first element
    if ordered_list[0] == item:
        return 0

    # Find range for binary search by repeated doubling
    index = 1
    n = len(ordered_list)
    while index < n and ordered_list[index] <= item:
        index *= 2

    # Do binary search in the found range
    return binary_search(ordered_list, index // 2, min(index, n - 1), item)

ordered_list = [3,5,8,10,15,26,35,45,56,80,120,125,138]
print(exponential_search(ordered_list, 125))
```
<img width="1202" height="179" alt="exponential_search" src="https://github.com/user-attachments/assets/e4eb0d71-995b-417e-be42-2538cf238da8" />

<img width="698" height="288" alt="binary_search" src="https://github.com/user-attachments/assets/d202505f-d8a7-4d96-b1c6-2b30e56d1d83" />

### Sorting

Sorting means rearranging data in ascending or descending order. Sorting is one of the most important algorithms in computer science and is widely used in database algorithms.

Examples:

* Bubble sort
* Insertion sort
* Selection sort
* Quicksort
* Timsort

#### bubble sort

Given an unordered list, we compare the adjacent elements of the list, and after each comparison, they are inserted in the correct order according to their values.

```python
def bubble_sort(arr):
    n = len(arr)
    print("Initial array:", arr)
    for i in range(n):
        swap = False
        print(f"Pass {i + 1}:")
        for j in range(0, n - 1 - i):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swap = True
                print(f"  Swapped {arr[j + 1]} and {arr[j]} --> {arr}")
            else:
                print(f"  No swap for {arr[j]} and {arr[j + 1]}")
        if not swap:
            print("  No swaps in this pass, array is sorted.")
            break
    print("Sorted array:", arr)

bs_arr = [6, 4, 9, 5, 7]
bubble_sort(bs_arr)
```

<img width="227" height="367" alt="bubble_sort" src="https://github.com/user-attachments/assets/7a8882d1-da6e-4c9d-9249-85b87744dbd3" />

#### insertion sort

The idea behind insertion sort is to maintain two sublists (a sublist is a portion of the original larger list), one sorted and the other unsorted, in which elements are added one by one from the unsorted sublist to the sorted sublist. Therefore, elements are removed from the unsorted sublist and inserted into the sorted sublist at the correct position, so that the sorted sublist remains sorted.

```python
def insertion_sort(arr):
    # Traverse from the second element (first element is already "sorted")
    for i in range(1, len(arr)):
        key = arr[i]          # Element to insert into the sorted sublist
        j = i - 1

        # Move elements of arr[0..i-1], that are greater than key,
        # one position ahead to make space for key
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key  # Insert key into its correct position
    return arr
```

#### selection sort

The idea behind insertion sort is to maintain two sublists (a sublist is a portion of the original larger list), one sorted and the other unsorted, in which elements are added one by one from the unsorted sublist to the sorted sublist. Therefore, elements are removed from the unsorted sublist and inserted into the sorted sublist at the correct position, so that the sorted sublist remains sorted.

```python
def selection_sort(arr):
    n = len(arr)

    for i in range(n):
        # Assume the first unsorted element is the smallest
        min_index = i

        # Find the index of the smallest element in the unsorted part
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        # Swap the found minimum with the first unsorted element
        arr[i], arr[min_index] = arr[min_index], arr[i]

    return arr


# Example usage
nums = [64, 25, 12, 22, 11]
print("Before:", nums)
print("After :", selection_sort(nums))
# Expected: [11, 12, 22, 25, 64]
```

#### quicksort

Quicksort is an algorithm based on the divide and conquer class of algorithms.


Choose a pivot element from the list (commonly the last element, first element, or median).
Partition the list so that:
* Elements smaller than pivot go to the left.
* Elements larger than pivot go to the right.
* Recursively apply quicksort on the left and right sublists.
* Combine results -> sorted array.

```python
def quicksort(arr):
    # Base case: arrays with 0 or 1 element are already sorted
    if len(arr) <= 1:
        return arr

    # Choose a pivot (here, last element)
    pivot = arr[-1]

    # Partition the array into three parts
    left = [x for x in arr[:-1] if x <= pivot]   # Elements <= pivot
    right = [x for x in arr[:-1] if x > pivot]   # Elements > pivot

    # Recursive step: sort left and right, then combine
    return quicksort(left) + [pivot] + quicksort(right)


# Example usage
nums = [10, 7, 8, 9, 1, 5]
print("Before:", nums)
print("After :", quicksort(nums))
```

#### Timsort

Timsort is a hybrid stable sorting algorithm, invented by Tim Peters in 2002. It combines the best parts of Merge Sort and Insertion Sort.

Divide into runs - The list is divided into small chunks (called runs):

* A run is either monotonically increasing or decreasing.
* If decreasing, it’s reversed to make it increasing.

Sort each run with insertion sort → Since insertion sort is efficient on small, nearly-sorted data.

Merge runs using merge sort → Like merge sort, repeatedly merge runs to form bigger sorted runs.

```python
def insertion_sort(arr, left, right):
    for i in range(left + 1, right + 1):
        key = arr[i]
        j = i - 1
        while j >= left and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key


# Merge function (like in merge sort)
def merge(arr, l, m, r):
    left = arr[l:m+1]
    right = arr[m+1:r+1]

    i = j = 0
    k = l

    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            arr[k] = left[i]
            i += 1
        else:
            arr[k] = right[j]
            j += 1
        k += 1

    # Copy remaining elements
    while i < len(left):
        arr[k] = left[i]
        i += 1
        k += 1

    while j < len(right):
        arr[k] = right[j]
        j += 1
        k += 1


def timsort(arr):
    n = len(arr)
    RUN = 32   # typical run size used in Timsort

    # Sort small runs with insertion sort
    for start in range(0, n, RUN):
        end = min(start + RUN - 1, n - 1)
        insertion_sort(arr, start, end)

    # Merge runs like merge sort
    size = RUN
    while size < n:
        for left in range(0, n, 2*size):
            mid = min(n - 1, left + size - 1)
            right = min((left + 2*size - 1), (n - 1))

            if mid < right:
                merge(arr, left, mid, right)

        size *= 2

    return arr


# Example usage
nums = [5, 21, 7, 23, 19, 12, 3, 1, 9, 8, 15, 4]
print("Before:", nums)
print("After :", timsort(nums))
# Expected: [1, 3, 4, 5, 7, 8, 9, 12, 15, 19, 21, 23]
```

### Selection Algorithms

Given a list of elements, selection algorithms are used to find the k-th smallest or largest element in the list. Therefore, given a list of data elements and a number (k), the goal is to find the k-th smallest or largest element.

* Sorting selection
* Randomized selection
* Deterministic selection

#### sorting selection

Simply sort the entire list, then pick the k-th element.

```python
def sorting_selection(arr, k):
    arr.sort()
    return arr[k-1]   # k-th smallest
```

#### randomized selection

Based on Quicksort’s partitioning.

Pick a random pivot, partition the array.
* If pivot index = k → found element.
* If k < pivot index → recurse on left.
* If k > pivot index → recurse on right.

```python
def randomized_selection(arr, k):
    if len(arr) == 1:
        return arr[0]

    pivot = random.choice(arr)
    
    left = [x for x in arr if x < pivot]
    right = [x for x in arr if x > pivot]
    equal = [x for x in arr if x == pivot]

    if k <= len(left):
        return randomized_selection(left, k)
    elif k <= len(left) + len(equal):
        return pivot
    else:
        return randomized_selection(right, k - len(left) - len(equal))
```

#### deterministic selection

Use median of medians to choose a good pivot. Guarantees that pivot splits array in a “balanced” way. Avoids worst-case of randomized selection.

Steps:

* Split list into groups of 5.
* Find the median of each group.
* Recursively find the median of medians → use as pivot.
* Partition using pivot.
* Recurse only into the side containing the k-th element.

```python
def deterministic_selection(arr, k):
    if len(arr) <= 5:
        return sorted(arr)[k-1]

    # Step 1: Split into groups of 5
    groups = [arr[i:i+5] for i in range(0, len(arr), 5)]
    medians = [sorted(group)[len(group)//2] for group in groups]

    # Step 2: Find pivot using median of medians
    pivot = deterministic_selection(medians, len(medians)//2 + 1)

    # Step 3: Partition
    left = [x for x in arr if x < pivot]
    right = [x for x in arr if x > pivot]
    equal = [x for x in arr if x == pivot]

    if k <= len(left):
        return deterministic_selection(left, k)
    elif k <= len(left) + len(equal):
        return pivot
    else:
        return deterministic_selection(right, k - len(left) - len(equal))
```

<img width="1066" height="142" alt="methods" src="https://github.com/user-attachments/assets/992ee02d-a3ad-4cc7-a0d0-c2c62b1f3127" />

| method | idea | average case | worst case | pros | cons |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Sorting Selection | Sort list, pick k-th | O(n log n) | O(n log n) | Simple | Wasteful if only one element needed |
| Randomized Selection (Quickselect) | Random pivot + partition | O(n) | O(n²) | Fast in practice | Bad pivot = worst case |
| Deterministic Selection (Median of Medians) | Median of medians pivot | O(n) | O(n) | Worst-case guarantee | Slower constants |

### String Search Algorithms

There are many popular string search algorithms. They have important applications, such as searching for an element in a text document, detecting plagiarism, using text editing programs, and so on. Brute-force algorithms and the Rabin-Karp, Knuth-Morris-Pratt (KMP), and Boyer-Moore pattern-finding algorithms are among the most popular.

#### brute force

Compare the pattern with the text starting at every possible position. If the pattern matches at position i, report it. Otherwise, move to the next position.

```python
def brute_force_search(text, pattern):
    n, m = len(text), len(pattern)
    for i in range(n - m + 1):
        if text[i:i+m] == pattern:
            return i
    return -1
```

#### Rabin–Karp

Uses hashing to speed up comparisons. Compute a hash of the pattern and compare it with hashes of substrings in the text. If hashes match → check actual substring to avoid collisions.

```python
def rabin_karp(text, pattern, prime=101):
    n, m = len(text), len(pattern)
    base = 256  # number of possible characters

    pattern_hash = 0
    text_hash = 0
    h = 1

    for _ in range(m-1):
        h = (h * base) % prime

    for i in range(m):
        pattern_hash = (base * pattern_hash + ord(pattern[i])) % prime
        text_hash = (base * text_hash + ord(text[i])) % prime

    for i in range(n - m + 1):
        if pattern_hash == text_hash:
            if text[i:i+m] == pattern:
                return i

        if i < n - m:
            text_hash = (base*(text_hash - ord(text[i])*h) + ord(text[i+m])) % prime

    return -1
```

#### Knuth–Morris–Pratt (KMP)

Avoids re-checking characters when a mismatch occurs. Builds a Longest Prefix Suffix (LPS) table to know how far to shift the pattern. More efficient than brute-force for repeated patterns.

```python
def kmp_search(text, pattern):
    n, m = len(text), len(pattern)

    # Build LPS table
    lps = [0] * m
    length = 0
    i = 1
    while i < m:
        if pattern[i] == pattern[length]:
            length += 1
            lps[i] = length
            i += 1
        elif length > 0:
            length = lps[length-1]
        else:
            lps[i] = 0
            i += 1

    # Search phase
    i = j = 0
    while i < n:
        if text[i] == pattern[j]:
            i += 1
            j += 1
            if j == m:
                return i - j
        else:
            if j > 0:
                j = lps[j-1]
            else:
                i += 1
    return -1
```

#### Boyer–Moore

Skips ahead in the text more aggressively than KMP. Uses two heuristics:

* Bad character rule → If mismatch occurs at char c, shift pattern so next occurrence of c in the pattern lines up.
* Good suffix rule → If suffix matches, shift pattern to align with next possible suffix.

```python
def boyer_moore_search(text, pattern):
    n, m = len(text), len(pattern)
    if m == 0:
        return 0

    # Bad character rule table
    bad_char = {c: -1 for c in set(text)}
    for i in range(m):
        bad_char[pattern[i]] = i

    s = 0
    while s <= n - m:
        j = m - 1
        while j >= 0 and pattern[j] == text[s+j]:
            j -= 1

        if j < 0:
            return s
        else:
            s += max(1, j - bad_char.get(text[s+j], -1))

    return -1
```

<img width="1034" height="159" alt="string_search_algorithms" src="https://github.com/user-attachments/assets/3f42cc45-0871-44cb-981a-0006d2c3f767" />

| algorithm | idea | average case | worst case | pros | cons |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Brute Force | Compare at every position | O(n·m) | O(n·m) | Simple | Very slow |
| Rabin-Karp | Hashing with rolling hash | O(n + m) | O(n·m) | Good for multi-pattern search | Hash collisions |
| KMP | Prefix-suffix (LPS) table | O(n + m) | O(n + m) | Guaranteed linear | Harder to implement |
| Boyer-Moore | Bad char + good suffix heuristics | O(n/m) best, fast in practice | O(n·m) | Very efficient in real cases | Complex rules |
