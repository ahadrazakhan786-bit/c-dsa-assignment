# C DSA Assignment — Ahad Raj Khan (BC202574)

# Theory and Complexity

## Q1. Stack Using Array

### Definition

A stack is a linear data structure that follows the **LIFO (Last In, First Out)** principle. The element inserted last is removed first.

In this implementation, an array stores the stack elements and the variable `top` keeps track of the current top position.

Initially:

```text
top = -1
```

This indicates that the stack is empty.

### PUSH(x)

`PUSH` inserts a new element at the top of the stack.

Algorithm:

1. Check whether `top == MAX - 1`.
2. If true, the stack is full and Stack Overflow occurs.
3. Otherwise, increment `top`.
4. Store the new element at `stack[top]`.

### POP()

`POP` removes the top element.

Algorithm:

1. Check whether `top == -1`.
2. If true, the stack is empty and Stack Underflow occurs.
3. Otherwise, read `stack[top]`.
4. Decrement `top`.

### PEEK()

`PEEK` returns or displays the top element without removing it.

Algorithm:

1. Check whether the stack is empty.
2. If it is empty, display an appropriate message.
3. Otherwise, display `stack[top]`.

### DISPLAY()

`DISPLAY` traverses the stack from `top` down to index `0` and displays the elements.

### Stack Complexity

| Operation | Time Complexity | Extra Space |
|---|---:|---:|
| PUSH | O(1) | O(1) |
| POP | O(1) | O(1) |
| PEEK | O(1) | O(1) |
| DISPLAY | O(n) | O(1) |

The array itself requires **O(n)** space, where `n` is the fixed capacity of the stack.

### Stack Overflow

Because the stack has a fixed capacity, attempting to insert an element when all positions are occupied causes **Stack Overflow**. The new element is not inserted.

For example, if the capacity is 5 and the stack already contains 5 elements, a sixth `PUSH` operation cannot be performed.

### Stack Underflow

If `POP` is called when the stack is empty, **Stack Underflow** occurs because there is no element available to remove.

---

## Q2. Circular Queue Using Array

### Definition

A queue is a linear data structure that follows the **FIFO (First In, First Out)** principle.

A circular queue connects the last array position back to the first position. Therefore, when the rear reaches the last index, it can wrap around to the beginning if free space is available.

The implementation uses:

- `front` — points to the first element.
- `rear` — points to the last element.

### Empty Condition

The queue is empty when:

```text
front == -1
```

### Full Condition

The queue is full when:

```text
(rear + 1) % MAX == front
```

The modulo operation makes the queue circular.

### ENQUEUE(x)

Algorithm:

1. Check whether the queue is full.
2. If full, report overflow.
3. If the queue is empty, set `front = 0`.
4. Move `rear` using `(rear + 1) % MAX`.
5. Insert the element at `queue[rear]`.

### DEQUEUE()

Algorithm:

1. Check whether the queue is empty.
2. If empty, report underflow.
3. Remove the element at `queue[front]`.
4. If `front == rear`, reset both to `-1`.
5. Otherwise, move `front` using `(front + 1) % MAX`.

### FRONT()

`FRONT` displays the element currently pointed to by `front` without removing it.

### DISPLAY()

Starting from `front`, the program moves through the queue using modulo arithmetic until `rear` is reached.

### Circular Queue Complexity

| Operation | Time Complexity | Extra Space |
|---|---:|---:|
| ENQUEUE | O(1) | O(1) |
| DEQUEUE | O(1) | O(1) |
| FRONT | O(1) | O(1) |
| DISPLAY | O(n) | O(1) |

The array used by the queue requires **O(n)** space for its fixed capacity.

---

## Circular Queue vs Linear Queue

### 1. Better Memory Utilization

In a simple linear queue, after several `DEQUEUE` operations, empty positions can appear at the beginning of the array. A normal linear implementation may still have `rear` at the last index, preventing new elements from being inserted even though unused positions exist at the beginning.

A circular queue solves this by wrapping `rear` back to the beginning and reusing those free positions.

### 2. Time Complexity

For a properly implemented array-based circular queue:

- `ENQUEUE` = **O(1)**
- `DEQUEUE` = **O(1)**

No shifting of elements is required.

### 3. Space Complexity

For a fixed array of capacity `n`, the queue requires **O(n)** space.

### 4. Problem in a Linear Queue

Consider a queue with capacity 5:

```text
[ _  _  30  40  50 ]
          ↑       ↑
        front    rear
```

The first two positions are unused, but if `rear` has already reached the last index, a basic linear queue cannot insert another element without shifting elements.

This can lead to a situation commonly called **false overflow**: the array contains unused positions, but the queue cannot use them because `rear` is at the last index.

A circular queue avoids this problem by wrapping around to the unused positions at the beginning.

---

## Conclusion

The assignment demonstrates two important array-based data structures:

1. A **Stack**, which follows LIFO and supports insertion/removal from one end.
2. A **Circular Queue**, which follows FIFO and efficiently reuses available array positions.

Both implementations use fixed-size arrays and handle their boundary conditions explicitly.
