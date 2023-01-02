## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 

# big O notation 
	describes the limiting behavior of a function when the argument tends towards a particular value or infinity, usually in terms of simpler functions. big O notation is used to classify algorithms by how they respond (e.g., in their processing time or working space requirements) to changes in input size.

## O(1) add item to array
	
	theArray[itemsInArray++] = newItem;

## O(N) linear search for value
	
	boolean valueInArray = false;
	StringBuilder indexsWithValue = new StringBuilder("");
	for(int i=0; i < arraySize;i++){
		if(theArray[i] == value{
		valueInArray = true;
		indexsWithValue.append(i).append(" ");
	}

## O(N^2)

	bubblesort
		
## O(logN)  binary search

## O(NlogN) 
	comparisons  = log n!
	comaprisons  = log n + log(n-1) + ... + log(1)
	comparisons = n log n

## O(n^2)

## O(n^3)

## O(2^N)
	
# data structure
	is a particular way of organizing data in a computer so that it can be used efficiently. efficient data structures are a key in designing efficient algorithms. 
	Array,Records(Tuples),map
		
## array /number of elements in specific order/
	array is a data structure consisting of a collection of elements ,identified by at least one array index/key. (String is example of array as it stores array of chars).
	http://en.wikipedia.org/wiki/Array_data_structure
	indexing o(1) (Good)
	insertion is not avaliable (Bad)
	waste space 0 (Good)
	

## map(for example: A hash table)
	name-value pairs can be added and deleted freely. 
	You can add,reassign,remove or lookup
	http://en.wikipedia.org/wiki/Associative_array

## set
	is an abstract data structure that can store specific values, without any particular order, and with no repeated values.(It is a computer implementation of the mathematical concept of a finite set. )Unlike most other collection types, rather than retrieving a specific element from a set, one typically tests a value for membership in a set.	
	
## Graphs and trees
	are linked abstract data structures composed of nodes. Each node contains a value and also one or more pointers to other nodes. 	

A tree
	is a non-linear data structure that consists of a root node and potentially many levels of additional nodes that form a hierarchy. A tree can be empty with no nodes called the null or empty tree or a tree is a structure consisting of one node called the root and one or more subtrees.
		Root - The top node in a tree.
		Parent - The converse notion of child.
		Siblings - Nodes with the same parent.
		Descendant - a node reachable by repeated proceeding from parent to child.
		Ancestor - a node reachable by repeated proceeding from child to parent.
		Leaf - a node with no children.
		Edge - connection between one node to another.
		Path - a sequence of nodes and edges connecting a node with a descendant.
		
Data type vs. data structure
	There is a distinction between a tree as an abstract data type and as a data structure, analogous to the distinction between a list and a linked list.

	As a data type, 
		a tree has a value and children, and the children are themselves trees; the value and children of the tree are interpreted as the value of the root node and the subtrees of the children of the root node. To allow finite trees, one must either allow the list of children to be empty (in which case trees can be required to be non-empty, an "empty tree" instead being represented by a forest of zero trees), or allow trees to be empty, in which case the list of children can be of fixed size (branching factor, especially 2 or "binary"), if desired.

	As a data structure,
		a linked tree is a group of nodes, where each node has a value and a list of references to other nodes (its children). This data structure actually defines a directed graph,[a] because it may have loops or several references to the same node, just as a linked list may have a loop. Thus there is also the requirement that no two references point to the same node (that each node has at most a single parent, and in fact exactly one parent, except for the root), and a tree that violates this is "corrupt".
	union
	???
	


list
  is an abstract data type that implements a finite ordered collection of values,

 
quicksort
	 is a divide-and-conquer method for sorting.
	it wrks by partitioning arrays so that smaller numbers are on the left and larger on the right.
	it recursively sends small parts of larger arrays to itself and partions again
	
divide and conquer (D&C)
	is an algorithm design paradigm based on multi-branched recursion. A divide and conquer algorithm works by recursively breaking down a problem into two or more sub-problems of the same (or related) type, until these become simple enough to be solved directly. The solutions to the sub-problems are then combined to give a solution to the original problem.

partitioning
	p
	
graph
	- nonempty finite set of verties V along with a set E of 2-element subsets of V.
		V - vertices - punkt
		E -Eages - linia ³¹cz¹ca 2 punkty ;P 
 
V={v1,v2,v3,v4,v5} E-{{v1,v2},{v1,v3},{v1,v4}

Cardinality of the Graph  is number of vertices |G| = 6
Degree of V1, deg(v1)=3 ( v1 has 3 eages)
G adjacency list
v1: v2,v3,v4
v2: v1,
..


tree doesn't have loops (isographic

 HashMap class is roughly equivalent to Hashtable, except that it is unsynchronized and permits nulls


Abstraction
is used to manage complexity. Software developers use abstraction to
decompose complex systems into smaller components. A

A class is a blueprint or prototype from which objects are created.

Inheritance provides a powerful and natural mechanism for organizing and structuring your softwar


DRY (Don't repeat yourself)

http://javarevisited.blogspot.co.uk/2012/03/10-object-oriented-design-principles.html

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
COMMON ORDER-OF-GROWTH CLASSIFICATIONS

Order of growth/name/typical code framework/description/example/T(2N)/T(N)
============================================================================
1		constant		a=b+c;			statement		add 2 numbers	1
============================================================================
log N	logarithmic		while(N>1)		dovide in half	binary search	~1
						{ N=N/2; ...}
============================================================================						
N		linear			for(...){...}	loop			find the max	2
============================================================================
N log N	linearithmic	Mergsort code	divide and		mergesort		~2
										conquer		
============================================================================										
N^2		quadratic		for(...){		double loop		check			4
							for(...){						all pair
							}
						}
============================================================================
N^3		cubic			for(...)		triple loop		check			8
							for(...)						all triples
							  for(...)
============================================================================							  
2^N		exponetial		see				exhaustive		check
						combinatorial	search				all subsets	T(N)
							search
============================================================================