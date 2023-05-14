
# Data Structures

Data structures are used to store and organise data. This is useful when it comes to arranging computer data so that it can be accessed efficiently. Data structures are also used for retrieving and processing data. Data structures consist of basic to advanced types which are used in almost every programming language.

*<a href="https://www.geeksforgeeks.org/data-structures/" target="_blank">GeeksForGeeks, Data Structures</a>*

----
## Lists

A `list` is a collection of items, stored in a single variable. The items in a list have an assigned index, starting from zero. The index identifies the item’s position in the list. Items can be added, edited, or removed from a list.

*<a href="https://www.w3schools.com/python/python_lists.asp" target="_blank">W3Schools, Python Lists</a>*

**Example in Python**
```python
# Create the list.
colours = ['Red', 'Green']

# Append 'Blue' to the end of the list.
colours.append('Blue')

print(colours)
```

**Output**
```Python
['Red', 'Green', 'Blue']
```

----
## Arrays

An `array` is a collection of items stored at the contiguous memory location. The purpose of arrays is to store multiple items of the same data type together. Each array element is uniquely identified by their index in the array.

*<a href="https://www.geeksforgeeks.org/array-data-structure/" target="_blank">GeeksForGeeks, Array Data Structure</a>*

**Example in Python**
```Python
# Import "array" since arrays are not built into Python.
from array import array
 
# Create integer arrays.
red_rgb = array('i', [255, 0, 0])
green_rgb = array('i', [0, 255, 0])
blue_rgb = array('i', [0, 0, 255])
 
# Loop through the arrays to print them.
for count in range(3):
    print(red_rgb[count], green_rgb[count], blue_rgb[count])
```

**Output**
```Python
255 0 0
0 255 0
0 0 255
```

----
## Linked lists

A `linked list` is a collection of items that are stored in a node. Each node has two fields: one field stores the data, whilst the other stores the address as a reference for the next node. The last node’s address reference is null since there is nothing to link to.

*<a href="https://www.simplilearn.com/tutorials/data-structure-tutorial/linked-list-in-data-structure" target="_blank">Simplilearn, Linked List in A Data Structure: All You Need to Know</a>*

**Example in Python**
```Python
# Declare Node class.
class Node:
    def __init__(self, value):
        self.value = value
        self.next_value = None

# Declare LinkedList class.
class LinkedList:
    def __init__(self):
        start_node = None

    # Method to print the linked list.
    def print_list(self):
        print_value = self.start_node
        while print_value is not None:
            print(print_value.value)
            print_value = print_value.next_value

# Create the linked list.
rgb_list = LinkedList()
# Instantiate start_node.
rgb_list.start_node = Node("Red")

# Create two other nodes.
rgb_green = Node("Green")
rgb_blue = Node("Blue")

# Link start_node's next_value to second node.
rgb_list.start_node.next_value = rgb_green
# Link second node to third node.
rgb_green.next_value = rgb_blue

rgb_list.print_list()
```

**Output**
```Python
Red
Green
Blue
```

*<a href="https://www.freecodecamp.org/news/introduction-to-linked-lists-in-python/" target="_blank">Example retrieved from freeCodeCamp, Linked Lists in Python - Explained with Examples</a>* 

----
## Stack

A `stack` is a data structure that follows an order that the operations are performed. The order can either be LIFO (Last In First Out) or FILO (First In Last Out). LIFO is when the element is inserted last, then comes out first. FILO is when the element is inserted first, then comes out last. 

Example of LIFO is when the plates are stacked over each other in a canteen. The plate at the top is the first one to be taken.

*<a href="https://www.geeksforgeeks.org/stack-data-structure/" target="blank_">GeeksForGeeks, Stack Data Structure</a>*

**Example in Python (LIFO order)**
```Python
# Create the stack list.
stack = []

# append() is used to push the item into stack.
stack.append('Red')
stack.append('Green')
stack.append('Blue')
print(stack)

# pop() is used to pop the item out of stack.
print("1:", stack.pop())
print("2:", stack.pop())
print("3:", stack.pop())

print(stack)
```

**Output**
```Python
['Red', 'Green', 'Blue']
1: Blue
2: Green
3: Red
[]
```

----
## Queues 

A `queue` is a data structure that opens at both ends and operates by FIFO (First In First Out) order. A queue is defined to a list so that all new additions are put at one end, while all deletions are made at the other end. The first element to be pushed into the list, is the first one to have operations performed on. 

*<a href="https://www.geeksforgeeks.org/queue-data-structure/" target="_blank">GeeksForGeeks, Queue Data Structure</a>*

**Example in Python**
```Python
# Import "queue" since queues are not built into Python.
from queue import Queue

# Create the queue.
rgb_queue = Queue()

# Put 'Red', 'Green', 'Blue' into queue in order.
rgb_queue.put('Red')
rgb_queue.put('Green')
rgb_queue.put('Blue')
print(rgb_queue.queue)

# Get the three colours in order they were put into queue.
print("1:", rgb_queue.get())
print("2:", rgb_queue.get())
print("3:", rgb_queue.get())

print(rgb_queue.queue)
```

**Output**
```Python
deque(['Red', 'Green', 'Blue'])
1: Red
2: Green
3: Blue
deque([])
```

----
## Trees

A `tree` is a data structure that sorts data so we can navigate through it easier. Trees use a collection of nodes that are connected to each other through relationships. The top node of a tree is called the root, and the nodes under it are called child nodes. Nodes can have multiple child nodes, and these child nodes can have their own child nodes. To simplify this, a tree can have roots, branches, and leaves connecting it all together. 

*<a href="https://www.geeksforgeeks.org/introduction-to-tree-data-structure-and-algorithm-tutorials/" target="_blank">GeeksForGeeks, Introduction to Tree – Data Structure and Algorithm Tutorials</a>*

**Example in Python**
```Python
class Tree(object):
    "Generic tree node."
    def __init__(self, name='root', children=None):
        self.name = name
        self.children = []
        if children is not None:
            for child in children:
                self.add_child(child)
    def __repr__(self):
        return self.name
    def add_child(self, node):
        assert isinstance(node, Tree)
        self.children.append(node)

t = Tree('*', [Tree('1'),
               Tree('2'),
               Tree('+', [Tree('3'),
                          Tree('4')])])
```

**Visual**
```Python
    *
   /|\
  1 2 +
     / \
    3   4
```

*<a href="https://stackoverflow.com/questions/2358045/how-can-i-implement-a-tree-in-python" target="_blank">Example retrieved from Stack Overflow, How can I implement a tree in Python? (third answer)</a>*

----
## Graphs

A `graph` is a data structure that consist of nodes and edges. The edges are lines that connect any two nodes in a graph. Graphs are used to represent networks. These networks may include paths, telephone networks or circuit networks. Graphs are also used in storage of information, each node is structured to store information like name, gender, phone number, etc. 

*<a href="https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/" target="_blank">GeeksForGeeks, Graph Data Structure And Algorithms</a>*

**Example in Python**
```Python
# Create the dictionary with graph elements
graph = { 
   "a" : ["b","c"],
   "b" : ["a", "d"],
   "c" : ["a", "d"],
   "d" : ["e"],
   "e" : ["d"]
} 
print(graph)
```

**Output**
```Python
{'a': ['b', 'c'], 'b': ['a', 'd'], 'c': ['a', 'd'], 'd': ['e'], 'e': ['d']}
```

**Visual**
```Python
'a'----'b'
 |      |
 |      |
'c'----'d'----'e'
```

*<a href="https://www.tutorialspoint.com/python_data_structure/python_graphs.htm" target="_blank">Example retrieved from Tutorials Point, Python - Graphs</a>*

----
## Sets

A `set` is a data structure that stores a collection of any type, of unique values in any order. Sets are different from arrays as sets only store the unique values. Sets can't store duplicate items of the same value.

*<a href="https://tutorialedge.net/compsci/data-structures/sets-for-beginners/" target="_blank">Tutorial Edge, Data Structures - Sets For Beginners</a>*

**Example in Python**
```Python
# Create the set.
rgb_set = {"Red", "Green", "Blue"}

# Attempting to add duplicate value to set.
rgb_set.add("Green")

print(rgb_set)
```

**Output**
```Python
{'Blue', 'Green', 'Red'}
```

----
## Hash tables

A `hash table` is a data structure that stores data in array format, each data value has its own unique index number. Hashing is a way to convert key values into indexes of an array. Accessing data in a hash table is incredibly fast if the index number is known for the data. This makes hash tables very useful when it comes to searching through data.

*<a href="https://www.tutorialspoint.com/data_structures_algorithms/hash_data_structure.htm" target="_blank">Tutorials Point, Data Structure and Algorithms - Hash Table</a>*

**Example in Python**
```Python
# Declare the dictionary.
red_dict = {'Name': 'Red', 'Value': "255, 0, 0"}
green_dict = {'Name': 'Green', 'Value': "0, 255, 0"}
blue_dict = {'Name': 'Blue', 'Value': "0, 0, 255"}

# Print the dictionary values by calling the keys.
print(red_dict['Name'], red_dict['Value'])
print(green_dict['Name'], green_dict['Value'])
print(blue_dict['Name'], blue_dict['Value'])

# Print the whole dictionary.
print(red_dict)
print(green_dict)
print(blue_dict)
```

**Output**
```Python
Red 255, 0, 0
Green 0, 255, 0
Blue 0, 0, 255
{'Name': 'Red', 'Value': '255, 0, 0'}
{'Name': 'Green', 'Value': '0, 255, 0'}
{'Name': 'Blue', 'Value': '0, 0, 255'}
```

----
