#Data structures, algorithms and concepts

#LINKED LIST & LISTS
* List of advantages
  * Linked List is Dynamic data Structure, can grow and shrink during run time.
  * Insertion and deletion operations are easier
  * Efficient Memory Utilization - no need to pre-allocate memory
  * Faster access time and can be expanded in constant time without memory overhead
  * linear data structures such as Stack,Queue can be easily implemeted using Linked list
* Linked lists have following drawbacks
  * Random access is not allowed. We have to access elements sequentially starting from the first node. So we cannot do binary search with linked lists.
  * Extra memory space for a pointer is required with each element of the list.
  * Reverse traversing is difficult
  * Memory is allocated to Linked List at run time if and only if there is space available in heap  
* Lists stores elements in successive order in memory.
  * Constant time for accessing an element at a specific index and adding new element at end


#STACK 
* Stack uses LIFO (Last in First Out) ordering
* Implementation can be using linked list or arrays. 
* Constant time to add and remove elements since no internal shifting around
* Does not offer constant time to access elements at position i unlike list/array
* Operations in constant time: push(), pop(), peek(), isEmpty(), size()  

#QUEUE 
* Queue uses FIFO (First in First Out) ordering
* Implementation can be using linked list or arrays. Linked Lists are preferred since access time can be kept constant. 
   All array elements need to get shifted after removing the first element.
* Constant time to add and remove elements since no internal shifting around
* Does not offer constant time to access elements at position i unlike list/array
* Operations in constant time: add(), remove(), peek(), isEmpty(), size()  


#TREES
* In computer science, a tree is a widely used abstract data type (ADT).
  A tree is a hierarchy (non-linear) data structure made up of nodes and edges where all nodes are connected without having any cycle
* A tree is a <bold>connected graph without the cycles</bold>
* Terminology  
    * <bold>Depth</bold> of a node is the length of the path (#nodes) from the <bold>root</bold> to the node
    * <bold>Height</bold> of a node is the length of the path (#nodes) from the node to the <bold>deepest</bold> node
       * Root node has a depth of zero
       * Leaf nodes have height one
       * Height of a tree is height of the root  
    * <bold>Size</bold> of binary tree is size of left subtree + 1 + size of right subtree
    * <bold>Diameter/width</bold>The diameter of a tree (sometimes called the width) is the number of nodes on the 
      longest path between two leaves in the tree 
    * <bold>Leaf</bold> is a node with no children.  

## TRIES (Prefix trees)
* Variation of n-ary tree in which characters are stored in each node. Each <bold>path down the tree</bold> may represent a word.
* A trie can check if a string is a valid prefix in O(K) time where K is the length of the string

##BINARY TREES
* A tree is a binary tree if <bold>each node has zero,one or two child nodes</bold>
* #Nodes at level h is 2^h
* #Total nodes is 2^h+1 - 1
* <bold>Complete Binary Tree:<bold> Each level is fully filled except perhaps for the last level. Example <bold>heap</bold>.
  Last level is filled left to right. All child nodes are height h or h-1      
* <bold>Full Binary Tree:</bold> Each node has <bold>exactly 2 child nodes</bold> or <bold>0</bold> child nodes 
* <bold>Perfect Binary Tree:</bold> <bold>Full and complete</bold>. Rare in real life and interviews.
* Depth First Traversal (DFT):  
	* Pre-order-Traversal: current node data ->left subtree -> right subtree
	* In-order-Traversal: <bold>Ascending order</bold> left subtree > current node data > right subtree
	* Post-order-Traversal:  left subtree > right subtree > current node data
* Breadth First Traversal (BFT): Visit nodes at each level starting with root.  

###BINARY SEARCH TREE (BST)
* left sub-tree elements are less than root
* right sub-tree elements are greater than root
* each node should satisfy this property
* The definition of BST can <bold>vary with respect to equality</bold>. Duplicates are not allowed by some definition. 
  In others, duplicate values will be on right or can be on eith side, <bold>clarify with your interviewer.</bold> 
* Compare BST vs Dictionary
    * BST finds elements closest to (not necessarily equal to) some arbitrary key value
    * BST iterates through the contents in sorted order (in-order traversal)
    * BST are memory-efficient, reserve more memory than they need to.
    * BST allows you to do range searches efficiently. 
    * Dictionary provides constant lookup time  

##HEAP
* Heap is a <bold>complete binary search tree</bold>
* Special properties of a heap are
  * Each node can have up to two child nodes
  * Value of the parent node must the >= or <= of child nodes
    * min heap - value of parent node is <strong>less than or equal to</strong> value of children. Root of the heap has maximum value
    * max heap - value of parent node is <strong>greater than or equal to</strong> value of children.  Root of the heap has maximum value
  * At level k (height, k > 0), there are a total of 2^k-1 nodes  
    * A leaf node at depth k (k > 0) can exist only if all nodes at depth k-1 exist 
    * Nodes at a partially filled level must be added from left to right
  * <strong>Binary Heap is a complete Binary tree where all levels except the lowest are completely full. </strong>
    * Maximum number of elements = 2^h+1 -1 . h is the height of the binary tree.
    * Minimum number of nodes = 2^h . h is the height of the binary tree.
* Heap Operations  
  * Parent of a node: For a node at ith position, parent is at  i-1//2 location  
  * Child of a node: For a node at ith position childrens are at 2*i + 1 and 2*i + 2 locations  
  * Delete: Only removing root node is permitted    
     * Copy root node (max value if max heap) to temp variable    
     * Copy last node to root  
     * Reduce heap size  
     * Pop (remove last element)  
     * Percolate down by comparing values  
  * Insert:   
     * Insert new node at end  
     * Increase heap size  
     * Percolate up by comparing values  
* <b>Heapify</b>: After inserting an element in a heap, the heap may not satisfy the heap property. 
  Location of nodes has to be changed to satisfy heap properties. Given a input (example:list) a heap can be built in linear time. 
* Complexity
  * Time complexity for delete and insert is O(log n), for n elements the complexity is O(nlogn)
  * Complexity to build a heap from array O(n) - If we start with the entire list the heap can be build in O(n)
* Heap Sort 
  * Two steps: Build heap & heapify
  * complexity: Best O(nlog(n)); Average O(nlog(n)); Worst O(nlog(n))
* Online Reference
  * [Heap Sort In Python](http://www.geekviewpoint.com/python/sorting/heapsort)
  * [Heap Sort on Bogotobogo](http://www.bogotobogo.com/Algorithms/heapsort.php)
  * [Heaps &amp; Binary Search Tree @Univ of Washington](http://courses.cs.washington.edu/courses/cse373/02au/lectures/lecture11l.pdf)
  * [Heaps Tutorial @Univ of Toronto](http://www.cs.toronto.edu/~krueger/cscB63h/w07/lectures/tut02.txt)
  * [Know Thy Complexities!](http://bigocheatsheet.com/)

#GRAPHS
* <bold>Connected Graph</bold> There is a path between every pair of vertex (nodes)
* <bold>Path</bold> in a graph is a finite or infinite sequence of edges which connect a sequence of vertices. 
  No <bold>vertices</bold> are repeated in a simple path.
* A cycle is a <bold>closed path</bold>. That is, we start and end at the same vertex and do not travel to any vertex twice  
* <bold>Acyclic graph</bold> is one without cycles (example: tree)
* Trail refer to a path where <bold>no edge</bold> is repeated
* Circuits refer to the <bold>closed trail</bold>, meaning we start and end at the same vertex