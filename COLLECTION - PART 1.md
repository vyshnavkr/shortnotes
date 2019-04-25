# THE BIG PICTURE OF COLLECTIONS AND GENERICS CHAPTER

## 1. equals() and hashCode(): To use in collections
 - why to learn them?: coz they are used in some collections
 - Methods of class Object?: toString(), equals(), hashCode(), wait(), notify(), notifyAll(), finalize())
 - == vs equals()
 - String (not StringBuilder & StringBuffer) and Wrappers have equals() implemented by default
 - why equals()?
 - implementing equals()
 - why hashCode()?
 - implementing hashCode() and points to note while implementing
 - when hashCode() fails? 
 

## 2. Basics of collections:
 - why collections?
 - Collection vs Collections vs collection
 - Ordered vs Sorted
 - collections hierarchy diagram. VERY IMPORTANT
	List: ordered items - index based
	 - ArrayList: fast iteration
	 - Vector: synchronized ArrayList
	 - LinkedList: fast insertion & deletion
	Set: unique items
	 - HashSet: u dont care about order and fast access performance
	 - LinkedHashSet: ordered HashSet - insertion based 
	 - TreeSet: sorted Set
	Map: key-value pairs of objects with unique keys
	 - HashMap: u dont care about order and fast access performance, allows 1 null key and multiple null values
	 - HashTable: synchronized HashMap, no null key/value
	 - LinkedHashMap: order HashMap - insertion/access based, slow insertion/deletion but fast iteration (opposite of LinkedList)
	 - TreeMap: sorted Map
	Queue: items to be processed in a FIFO manner (check)
	 - PriorityQueue: instead of FIFO, items process in ascending/Comparator order (check)
 
 
## 3. Using the Collections Framework:
 - Array vs ArrayList
 - AutoBoxing with collections
 - Sorting and Searching Arrays and collections
 - How to convert: Array -> List;	List/Set -> Array
 - Using List, Set, Map
 - Using TreeSet & TreeMap: 
	- Searching methods: higer, lower, ceiling, floor, poll
	- Reversing method: descending
	- Creating a smaller copy: sub, head, tail
 - PriorityQueue:
	- creating a PriorityQueue: either in natural order or using Comparator
	- operations on PriorityQueue: peek, poll, offer(means insert)
	- Details of natural ordering
 - Map functions, Map.Entry functions, Loop through Map
 
 
## 4. GENERICS:
 - Why generics? 2 reasons: type-safety, and code reusability/avoid redundancy
 - To use Generic code with Legacy code: Java gives TypeErasure. Thus, no runtime protection
 - No Polymorphism in Generics, coz of compile-time protection due to TypeErasure. (But Array allows Polymorphism because it has Runtime protection    via ArrayStoreException) 
 - Bounded Type Parameter, Multiple BTP, Wildcard, Upper Bounded Wildcard, Lower Bounded Wildcard: ?, extends, super and add()
 - Generic Class, Generic method, Generic Constructor
 - link: https://www.codejava.net/java-core/collections/how-to-write-generic-classes-and-methods-in-java
