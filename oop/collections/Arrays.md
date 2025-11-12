The Java Collection Framework (JCF) is a unified architecture that provides:

Interfaces to define data structures and operations

Classes to implement them

Algorithms to perform operations such as sorting and searching

It simplifies data handling by providing reusable and efficient data structures.

🔹 Key Components:
Component	Description
Interfaces	Abstract data types (e.g., List, Set, Map)
Implementations	Concrete classes (e.g., ArrayList, HashMap)
Algorithms	Utility methods in Collections class (e.g., sort, reverse)
🔹 Package:

All classes and interfaces are present in java.util.

🔹 Difference Between Array and Collection
Feature	Array	Collection
Size	Fixed	Dynamic
Data Type	Same type	Can be heterogeneous
Memory Management	Manual	Automatic
Performance	Fast but limited	Slightly slower but flexible
Ready-made methods	None	Many built-in methods
🧠 Interview Questions

What are the main advantages of using the Collection Framework?

Why is Collection Framework better than arrays?

How does Collection improve code reusability?

🧱 2. Collection Hierarchy
                  Iterable
                      │
                 Collection
              ┌────────┼────────┐
             List      Set     Queue
              │         │        │
       ArrayList   HashSet   PriorityQueue
       LinkedList  LinkedHashSet  ArrayDeque
       Vector      TreeSet
       Stack


Separate Hierarchy:

                   Map
        ┌──────────┼──────────┐
     HashMap   LinkedHashMap   TreeMap
