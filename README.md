# College Canteen Order System

A web app that handles canteen orders in the order students place them, using a **circular queue**.

**Live demo:** _paste your GitHub Pages link here_

## DSA concept: Queue (circular, array-based)

Orders must be prepared first-come, first-served (FIFO). The queue is stored in a fixed array of 8 slots with two indices:

- `rear` is where the next order is stored. After the last slot it **wraps around** to slot 0 using `(rear + 1) % capacity`.
- `front` is the oldest waiting order. After it is served, `front` moves forward with `(front + 1) % capacity`.

Because the indices wrap, slots freed at the front get reused, so the array never needs to shift its elements. The queue is full only when all 8 slots hold orders.

| Operation | Use in the app | Time |
|-----------|----------------|------|
| `enqueue` | Place an order in the next free slot | O(1) |
| `dequeue` | Send the oldest order to the kitchen | O(1) |
| `peek` | Look at the oldest order without removing it | O(1) |
| `isFull` / `isEmpty` | Reject orders when full, disable the kitchen button when empty | O(1) |

## Features
- Place orders with a student name and menu item
- Slot view that highlights the `front` and `rear` slots and shows the wrap-around
- Kitchen progress bar, then a "ready for pickup" list
- Full-queue message when all 8 slots are taken, plus an operation log

## Run it
Open `index.html` in a browser. No install or build step.

## Tech
HTML, CSS, and vanilla JavaScript in a single file.
