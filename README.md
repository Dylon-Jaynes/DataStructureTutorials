
Let’s take a look at our first data structure, a “Set”. 


Sets are an unordered collection data type which is iterable, immutable, can contain data of all types, and cannot contain duplicates. These properties of a set allow us to do things such as removing duplicate items from data structures that allows duplicates such as a List, a Tuple, or even a String. They allow us to check for membership efficiently as they are optimized for such operations *(average time complexity is O(1) as opposed to O(n) for lists).* Sets are also commonly used to perform certain math operation like a union or an intersection.

There is a common “gotcha” to consider when using sets. While sets can contain data of all types, sets cannot contain a data type that is not hashable. This means that you cannot insert a list or a set into a set. Instead of a list or a set, you must use a tuple or a frozenset as they can be hashed. This is because the data contained within a set must be immutable, meaning it can’t be changed. 

Now that we understand what a set is, let’s take a look at some built-in methods along with their time complexity. *\*Note, this is not a comprehensive list.*




|**Function**  |**Description**  |**Big O Notation**|
| :- | :- | :- |
|add()  |Adds an element to the set. |O(1)|
|clear()  |Removes all the elements from the set. |O(1)|
|copy()  |Returns a copy of the set. |O(n)|
|len()  |Returns the length of the set. |O(1)|
|symmetric\_difference()|Returns the symmetric difference of two sets as a new set.|O(n)|
|difference()  |Returns a set containing the difference between two or more sets. |O(n)|
|intersection()  |Returns the intersection of two other sets. |O(n)|
|union()  |Returns a set containing the union of sets. |O(n)|
|discard()  |Removes the specified element. |O(1)|
|remove()  |Removes the specified element, throws an error if the element does not exist. |O(1)|
|<p>pop()  </p><p></p>|Removes a random element from the set and returns it. |O(1)|




Below we have a diagram taken from cloudinary.com which illustrates difference(), symmetric\_difference(), intersection(), and union() functions.


Knowing what a set is, let’s look at an example:

Imagine that you have a set of current faculty member names for each year between 2018 and 2021. You are tasked with getting all of the faculty names from 2018 – 2021 into one data structure without any duplicates. Order is not important in this case.

Here are the sets of names:

```   
set2018 = {"Jeremy", "Melissa", "Cole", "Roger", "Mathew"}

set2019 = {"Jeremy", "Melissa", "Kent", "Jason", "Mathew", "Barbara"}

set2020 = {"Melissa", "Kent", "Jason", "Keith", "Dylon", "Jackson", "Brandon"}
    
set2021 = {"Brandon", "Bethany", "Mike", "Keith", "Mia", "Fred", "George", "Timothy"}
```


This is a very simple problem that can be solved in one line with a sets union() method. 

```
set2018To2021 = set2018.union(set2019, set2020, set2021)
```

This single line of code stores all of the unique names from all the sets into one unordered set. You can then simply display the names using print().

Now try and solve the following problem on your own. You have 3 lists that contains the elements from the periodic table that are used in 3 separate scientific experiments. You need to get all the elements that were used in all 3 of those experiments into a data structure with no duplicate elements. Order is not important.

Here are the lists of elements.

```
elementList1 = ["Be", "Mg", "Ni", "He", "Se"]

elementList2 = ["Be", "Mg", "Ru", "Mo", "Pb", "In", "Lv", "Po"]

elementList3 = ["Pb", "Ds", "Mc", "Mo", "Po", "At", "Xe"]
```
    
Click the following link for the solution. 

[Sets Example Solution](SetsCodeExampleSolution.md)
