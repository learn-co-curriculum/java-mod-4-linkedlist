# LinkedList

## Learning Goals

- Understand the difference between an ArrayList and a LinkedList.
- Create, add, retrieve, and remove elements from a LinkedList.

## What is a LinkedList?

A LinkedList is a group of ordered elements that allows duplicates, can be
dynamically resized, and is mutable.

A LinkedList is made up of linked nodes. Each node instance contains the element
and references to both the previous and next node. Here’s what a Node class
looks like:

```java
class Node<E> {
    E element;
    Node<E> next;
    Node<E> prev;

    Node(Node<E> prev, E element, Node<E> next) {
        this.element = element;
        this.next = next;
        this.prev = prev;
    }
}
```

- `element` - contains the data that needs to be stored by a Node
- `next` - pointer to the next Node
- `prev` - pointer to the previous Node

This type of linked lists are called doubly linked lists since each Node has two
references, one to the previous Node and one to the next Node.

## Creating a LinkedList

We can create LinkedList similar to how we create ArrayLists. An empty
LinkedList can be created or an existing collection can be used to create a new
LinkedList.

```java
import java.util.Arrays;
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> emptyList = new LinkedList<>();
        LinkedList<String> names = new LinkedList<String>(Arrays.asList(
                "Tommy",
                "Rufus",
                "Luna"
        ));

        System.out.println(emptyList); // -> []
        System.out.println(names); // -> [Tommy, Rufus, Luna]
    }
}
```

**NOTE:** Although the LinkedList is printed out as an array it’s still a
LinkedList.

## Adding Elements

A LinkedList allows us to add elements at the beginning and end of the
LinkedList with O(1) time complexity. We can also insert elements at specific
indexes and insert multiple elements like we can for ArrayLists.

### Adding Elements at the Ends

The `add(E e)` and the `addLast(E e)` both add elements at the end of the
LinkedList.

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> pets = new LinkedList<>();
        pets.add("Mimi");
        pets.add("Rocky");
        pets.addLast("Milo");

        System.out.println(pets); // -> [Mimi, Rocky, Milo]
    }
}
```

The `addFirst(E e)` method adds elements at the beginning of the list.

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> pets = new LinkedList<>();
        pets.add("Mimi");
        pets.add("Rocky");
        pets.addLast("Milo");

        System.out.println(pets); // -> [Mimi, Rocky, Milo]

        pets.addFirst("Lola");
        pets.addFirst("Cooper");
        System.out.println(pets); // -> [Cooper, Lola, Mimi, Rocky, Milo]
    }
}
```

### Adding Elements at a Specific Index

The `add (int index, E element)` insert the `element` at the given `index`.

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> pets = new LinkedList<>();
        pets.add("Mimi");
        pets.add("Rocky");
        pets.addLast("Milo");

        System.out.println(pets); // -> [Mimi, Rocky, Milo]

        pets.add(1, "Lola");
        pets.add(3, "Lulu"); // -> [Mimi, Lola, Rocky, Lulu, Milo]

        System.out.println(pets);
    }
}
```

## Retrieving Elements

Elements can be retrieved from the beginning, end, or from a specific index in
the LinkedList.

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> pets = new LinkedList<>();
        pets.add("Mimi");
        pets.add("Rocky");
        pets.addLast("Milo");

        System.out.println(pets); // -> [Mimi, Rocky, Milo]
        System.out.println(pets.getFirst()); // -> Mimi
        System.out.println(pets.getLast()); // -> Milo
        System.out.println(pets.get(1));    // -> Rocky
    }
}
```

## Removing Elements

There are similar methods to the `get` methods above for removing elements.

```java
import java.util.LinkedList;

public class Playground {
    public static void main(String[] args) {
        LinkedList<String> pets = new LinkedList<>();
        pets.add("Mimi");
        pets.add("Rocky");
        pets.add("Milo");
        pets.add("Clyde");
        pets.add("Daisy");

        pets.removeFirst(); // -> removes "Mimi"
        pets.removeLast(); // -> removes "Daisy"
        System.out.println(pets); // -> [Rocky, Milo, Clyde]
        pets.remove(2); // -> removes "Clyde"
        System.out.println(pets); // -> [Rocky, Milo]
    }
}
```

## References

- [LinkedList Java Docs](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/LinkedList.html)
