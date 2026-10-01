# C DSA Assignment — Stack & Circular Queue

**Student Name:** Ahad Raj Khan  
**Student ID:** BC202574  
**Course:** BCA  
**Semester:** 3  
**Language:** C  
**Data Structure:** Stack and Circular Queue  
**Submission Type:** GitHub Repository  
**Deadline:** 7 October 2026

## Assignment Overview

This repository contains the complete implementation and theoretical explanation for the two compulsory questions in the C DSA assignment.

## Student Details

| Field | Details |
|---|---|
| **Name** | Ahad Raj Khan |
| **Student ID** | BC202574 |
| **Course** | BCA |
| **Semester** | 3 |
| **Section** | F |

### Q1 — Stack Using Array

The stack is implemented using a fixed-size array without using any built-in stack library.

Supported operations:

- `PUSH(x)`
- `POP()`
- `PEEK()`
- `DISPLAY()`

The program handles:

- Stack Overflow
- Stack Underflow

### Q2 — Circular Queue Using Array

The circular queue is implemented using a fixed-size array.

Supported operations:

- `ENQUEUE(x)`
- `DEQUEUE()`
- `FRONT()`
- `DISPLAY()`

The implementation correctly distinguishes between a full queue and an empty queue.

## Repository Structure

```text
c-dsa-assignment/
├── README.md
├── src/
│   ├── stack_array.c
│   └── circular_queue.c
└── docs/
    └── theory.md
```

## How to Compile and Run

You need a C compiler such as GCC.

### Stack

```bash
gcc src/stack_array.c -o stack
./stack
```

On Windows:

```bash
gcc src/stack_array.c -o stack.exe
stack.exe
```

### Circular Queue

```bash
gcc src/circular_queue.c -o circular_queue
./circular_queue
```

On Windows:

```bash
gcc src/circular_queue.c -o circular_queue.exe
circular_queue.exe
```

## Example Stack Test

Try:

1. PUSH 10
2. PUSH 20
3. PUSH 30
4. PEEK
5. DISPLAY
6. POP
7. DISPLAY

To test overflow, push more than 5 elements.

To test underflow, keep popping until the stack is empty and then call POP again.

## Example Circular Queue Test

Try:

1. ENQUEUE 10
2. ENQUEUE 20
3. ENQUEUE 30
4. FRONT
5. DISPLAY
6. DEQUEUE
7. ENQUEUE 40
8. DISPLAY

The circular implementation reuses positions that become free after `DEQUEUE`.

## Theory

Detailed explanations, algorithms, complexity analysis, and the comparison between a circular queue and a linear queue are available in [`docs/theory.md`](docs/theory.md).

## Submission

Upload this repository to GitHub and submit the repository URL as your assignment submission.
