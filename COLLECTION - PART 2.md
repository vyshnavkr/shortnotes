					# Using the Collections Framework

## Array vs ArrayList

## Autoboxing with Collections
 - now with java6 you can even add a primitive to a collection (from java6 primitive gets autoboxed to wrapper)
						
## Sorting and Searching Arrays and Collections: 
 - read COLLECTION - PART 3
### Ordered vs Sorted
 - Ordered Collection (index/insertion/access order) 
 - Sorted Collection (natural order: aplha/num/Comparable, external order: Comparator) 
### sort 
 - Arrays.sort()(Either Comparable or Comparator used), 
 - Collections.sort() (only lists)(Either Comparable or Comparator used), 
 - TreeSet/TreeMap (Either Comparable or Comparator used)
### search
   Arrays.binarySearch(), Collections.binarySearch()
							
## Converting Arrays to Lists, and Lists/Sets to Arrays
### Arrays.asList()
### list.toArray() or set.toArray() or list.toArray(new int[0]) or set.toArray(new int[5])

## Using List :
### Iterator: hasNext(), next(), casting
 - Iterator iterator = listObject.iterator();
 - (Similarly for Set and Map:
    - Iterator iterator = setObject.iterator();
    - Iterator<Map.Entry<String, String>> iterator = mapObject.entrySet().iterator();)

## Using Set:
### add() -> returns false if item already present
### hashset -> no order
### treeset -> 
	- WHENEVER YOU WANT A COLLECTION TO BE SORTED, ITS ELEMENTS MUST BE OF SAME TYPE
	- not generically declared - ClassCastException will be thrown at the addition of "separate type element". (eg: first stringObject added, and 	  then integerObject. But integerObject can't be compared with stringObject in compareTo())
	- generically declared - Compiler Error at the addition of separate type element (sameClass and subClasses can be added)
	- for user-defined objects - the object added (ie, the argument inside add()) must implement Comparable and override compareTo() (else 	  	  	  ClassCastException will be thrown at the addition of "first element" 
	- for String and Wrappers - Comparable is overriden by default
	- All these are same for PriorityQueue


## Using Map
### CONCEPT: 
 - how Map is dependent on haschCode() and equals(), how modifying variables used in the implementation of haschcode() and equals() affect 	   searching of an element in a HashMap/LinkedHashMap


## Using TreeSet and TreeMap:
### Searching values from TreeSets and TreeMaps:
	- treeSet.lower(1600), higher, ceiling(), floor()       	[suffix 'Key' for Map]
	- pollFirst(), pollLast()					[suffix 'Entry' for Map]
	- descendingSet()						[suffix 'Map' for Map]
							
### Creating sub groups from TreeSet and TreeMap / Backed Collections: 
	- when used? when you need a smaller portion of a sorted collection rather than the entire collection, 
	  you create a copy of the original collection with smaller portion
	- TreeSet: subSet(), headSet(), tailSet()
	- TreeMap: subMap(), headMap(), tailMap()
	- modifying either the original or the copy will be automatically reflected on the other (condition: within the range of copy). 


## Priority Queue
### Creating a PQ with:
	- natural order (ascending order for alphabets and numbers)
	- Comparator order

### Operations on PQ: 
 - peek(), poll(), offer()
						
### Details of Natural Ordering: 
 - "space" has more priority than "characters". "UPPERCASE" has more priority than "lowercase".


## Map functions
### read entire keys/values/entries:
 - entrySet() -> returns a Set of all the entries
 - keySet() -> returns a Set of all the keys
 - values() -> returns a Collection of all the values

### read/write an entry:
 - put(key, value); 
 - get(key) -> returns the "value" to which the specified "key" is mapped, or null if this map contains no mapping for the key.


## Map.Entry functions
### read and write operations:
 - getKey() -> returns the key corresponding to this "entry"
 - getValue() -> returns the value corresponding to this "entry"
 - setValue() -> sets the value corresponding to this "entry"


## Loop Through Map
### using iterator
 - Iterator it = map.entrySet().iterator();
```
   while (it.hasNext()) {
       Map.Entry entry = (Map.Entry)it.next();
       System.out.println(entry.getKey() + " = " + entry.getValue());
   }
```

### using for-each loop:
```
   Map<Integer, Integer> map = new HashMap<Integer, Integer>();
   for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
       System.out.println("Key = " + entry.getKey() + ", Value = " + entry.getValue());
   }
```
