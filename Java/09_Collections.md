# 09 – Collections Framework

## What is the Collections Framework?
A set of classes and interfaces in `java.util` that provide ready-to-use **data structures**.
Unlike arrays, most collections are **dynamic** (grow/shrink automatically).

## Key Interfaces
```
Collection
├── List   (ordered, allows duplicates)  → ArrayList, LinkedList
├── Set    (unordered, no duplicates)    → HashSet, TreeSet
└── Queue  (FIFO ordering)              → LinkedList, PriorityQueue

Map (key-value pairs, keys unique)       → HashMap, TreeMap, LinkedHashMap
```

---

## List – ArrayList
```java
import java.util.ArrayList;

ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Cherry");

System.out.println(fruits.get(1));    // Banana
System.out.println(fruits.size());    // 3

fruits.remove("Banana");
System.out.println(fruits);           // [Apple, Cherry]

// Iterating
for (String f : fruits) {
    System.out.println(f);
}
```

## List – LinkedList
```java
import java.util.LinkedList;

LinkedList<Integer> list = new LinkedList<>();
list.addFirst(10);
list.addLast(20);
list.add(15);

System.out.println(list.getFirst());  // 10
System.out.println(list.getLast());   // 20
list.removeFirst();
```

---

## Set – HashSet
```java
import java.util.HashSet;

HashSet<String> set = new HashSet<>();
set.add("Java");
set.add("Python");
set.add("Java");    // duplicate – ignored

System.out.println(set.size());       // 2
System.out.println(set.contains("Python"));  // true
```

---

## Map – HashMap
```java
import java.util.HashMap;

HashMap<String, Integer> scores = new HashMap<>();
scores.put("Alice", 90);
scores.put("Bob", 85);
scores.put("Charlie", 92);

System.out.println(scores.get("Bob"));     // 85
System.out.println(scores.containsKey("Alice")); // true

scores.remove("Bob");

// Iterating over a Map
for (String key : scores.keySet()) {
    System.out.println(key + " → " + scores.get(key));
}
```

---

## Queue – LinkedList as Queue
```java
import java.util.Queue;
import java.util.LinkedList;

Queue<String> queue = new LinkedList<>();
queue.offer("First");
queue.offer("Second");
queue.offer("Third");

System.out.println(queue.peek());    // First (view without removing)
System.out.println(queue.poll());    // First (remove and return)
System.out.println(queue.size());    // 2
```

---

## Stack
```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.push(2);
stack.push(3);

System.out.println(stack.peek());    // 3 (top element)
System.out.println(stack.pop());     // 3 (remove top)
System.out.println(stack.isEmpty()); // false
```

---

## Sorting Collections
```java
import java.util.Collections;
import java.util.ArrayList;

ArrayList<Integer> nums = new ArrayList<>();
nums.add(5); nums.add(2); nums.add(8); nums.add(1);

Collections.sort(nums);
System.out.println(nums);                   // [1, 2, 5, 8]

Collections.sort(nums, Collections.reverseOrder());
System.out.println(nums);                   // [8, 5, 2, 1]

System.out.println(Collections.max(nums));  // 8
System.out.println(Collections.min(nums));  // 1
```

---

## Choosing the Right Collection
| Need                             | Use           |
|----------------------------------|---------------|
| Ordered list, fast random access | `ArrayList`   |
| Frequent insert/delete (front)   | `LinkedList`  |
| No duplicates                    | `HashSet`     |
| Sorted set                       | `TreeSet`     |
| Key-value pairs                  | `HashMap`     |
| Sorted key-value pairs           | `TreeMap`     |
| FIFO queue                       | `Queue`       |
| LIFO stack                       | `Stack`/`Deque` |
