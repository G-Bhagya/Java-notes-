The List interface is part of the java.util package.
It extends the Collection interface and represents an ordered, indexed, and duplicate-allowing collection of elements.

1️⃣ Hierarchy
java.lang.Object
   ↳ java.util.Collection
        ↳ java.util.List


List is a child of Collection, so it inherits all methods from Collection.

2️⃣ Characteristics of List
✔ 1. Ordered Collection

List stores elements in a specific order.

Insertion order is maintained.

Example: If you add elements in this order → 10, 20, 30
It will remain in the same order unless changed.

✔ 2. Index Based Access

Every element is associated with an index (0 to size-1).

You can:

get elements → list.get(index)

modify elements → list.set(index, element)

insert at position → list.add(index, element)

remove at position → list.remove(index)

✔ 3. Allows Duplicates

List can store duplicate elements.

Example: [10, 20, 20, 30] is valid.

✔ 4. Allows Multiple Nulls

Some implementations (ArrayList, LinkedList) allow multiple null elements.

Vector also allows nulls.

✔ 5. Supports Iteration

You can iterate using:

for loop

enhanced for

Iterator

ListIterator (forward + backward traversal)

✔ 6. Supports Random Access (depending on implementation)

ArrayList → Fast random access (O(1))

LinkedList → Slow random access (O(n))

3️⃣ Methods of List Interface (All Important Methods)

Here is a complete method list with explanations:

🔵 A. Adding Elements
1. add(E e)

Adds element at end.

Example: list.add("A")

2. add(int index, E element)

Inserts element at a specific index

Shifts other elements to the right.

3. addAll(Collection c)

Adds all elements of another collection.

4. addAll(int index, Collection c)

Inserts a group of elements starting at a specific index.

🔵 B. Accessing Elements
5. get(int index)

Returns the element at given index.

🔵 C. Updating Elements
6. set(int index, E element)

Replaces the existing element at index with a new value.

Returns old value.

🔵 D. Removing Elements
7. remove(int index)

Removes element at given index.

Returns removed element.

8. remove(Object o)

Removes first occurrence of the object.

9. clear()

Removes all elements from the list.

🔵 E. Searching and Checking
10. contains(Object o)

Checks if element exists.

11. indexOf(Object o)

Returns first index of object (or -1 if not found).

12. lastIndexOf(Object o)

Returns last index of object.

🔵 F. Size and Utility Methods
13. size()

Number of elements.

14. isEmpty()

Returns true if list has no elements.

🔵 G. Iterators
15. iterator()

Returns Iterator (forward only).

16. listIterator()

Returns ListIterator (forward + backward).

17. listIterator(int index)

ListIterator starting at given index.

4️⃣ Implementing Classes of List Interface

The important classes that implement List are:

🔶 1. ArrayList

Backed by dynamic array.

Fast random access → O(1).

Slow insert/delete in middle → O(n).

Allows duplicates + null.

Not synchronized (not thread-safe).

🔶 2. LinkedList

Backed by doubly linked list.

Fast insert/delete → O(1).

Slow random access → O(n).

Can act as List, Queue, Deque.

Allows duplicates + null.

🔶 3. Vector

Dynamic array like ArrayList.

Synchronized → thread-safe but slow.

Legacy class.

🔶 4. Stack

Child of Vector.

LIFO (Last-In-First-Out)

Methods: push(), pop(), peek()

5️⃣ Internal Working (Important for Interviews)
A. ArrayList Internal Working

Uses resizable array.

Default capacity = 10.

If full → grows by 50% (Java 8+).

Access → O(1)

Insert at end → O(1) amortized

Insert at position → O(n)

B. LinkedList Internal Working

Each node has:

data

next pointer

previous pointer

No capacity issue.

Insert/delete → O(1)

Access → O(n)

C. Vector Internal Working

Array like ArrayList.

Synchronized → thread safe.

Grows by 100% (doubles size).

6️⃣ Differences (Very Important)
🔶 List vs Set
List	Set
Ordered	Unordered
Allows duplicates	No duplicates
Has index	No index
Example: ArrayList	HashSet
🔶 ArrayList vs LinkedList
Feature	ArrayList	LinkedList
Storage	Array	Linked nodes
Access	Fast (O(1))	Slow (O(n))
Insert/Delete	Slow	Fast
Memory	Compact	More memory (pointers)
🔶 ArrayList vs Vector
ArrayList	Vector
Not synchronized	Synchronized
Fast	Slow
Modern	Legacy
7️⃣ Advantages of List

✔ Maintains insertion order
✔ Allows duplicates
✔ Provides index-based access
✔ Flexible methods (add, remove, update, search)
✔ Several implementations available (ArrayList, LinkedList, etc.)

8️⃣ Disadvantages of List

✘ Uses more memory than arrays
✘ Operations can be slow (depending on type)
✘ Not synchronized by default
✘ IndexOutOfBoundsException if index is invalid

9️⃣ When to Use Which List
✔ Use ArrayList when:

More reads, fewer inserts

Need fast access

✔ Use LinkedList when:

Many insert/delete operations

Queue/Deque operations needed

✔ Use Vector when:

Need thread safety

Using legacy code

🔟 List Example (Complete Code)
import java.util.*;

public class ListDemo {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        
        list.add("A");
        list.add("B");
        list.add("C");
        list.add("A"); // duplicates allowed
        
        System.out.println(list); // [A, B, C, A]

        System.out.println(list.get(2));  // C

        list.set(1, "Z"); 
        System.out.println(list); // [A, Z, C, A]

        list.remove(3);
        System.out.println(list); // [A, Z, C]
        
        System.out.println(list.contains("C")); // true
        
        System.out.println(list.indexOf("A")); // 0
        System.out.println(list.lastIndexOf("A")); // 0 (after removal)
    }
}
