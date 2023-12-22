# Python Threading

Python threading allows you to run different parts of your program concurrently and can be used to speed up processing times in some scenarios, particularly for I/O-bound and high-latency operations. Here's a brief overview before we dive into the examples:

### Why Use Threads in Python?
1. **Concurrent Execution**: Threads can be used to execute tasks concurrently. This is particularly useful in I/O-bound applications where you can perform other operations while waiting for I/O operations to complete.
2. **Improved Responsiveness**: In a GUI application, threading can be used to keep the UI responsive while performing background tasks.
3. **Resource Sharing**: Threads within the same process share memory and resources, facilitating communication and data sharing.

### What are Threads in Python?
- Python threads are a form of parallelism that allows your program to run multiple procedures at once.
- Threads are lighter than processes, and share the same memory space.

### How to Use Threads in Python?
- Python's `threading` module is used to create and manage threads.
- Basic operations include creating, starting, and joining threads.

### Examples of Python Threads
I'll start with simple examples and gradually move to more complex ones. Here are the first few examples:

#### Example 1: Basic Thread Creation
```python
import threading

def print_numbers():
    for i in range(1, 6):
        print(i)

# Create a thread
thread = threading.Thread(target=print_numbers)

# Start the thread
thread.start()

# Wait for the thread to finish
thread.join()
```

#### Example 2: Passing Arguments to Threads
```python
def print_range(start, end):
    for i in range(start, end):
        print(i)

# Create a thread with arguments
thread = threading.Thread(target=print_range, args=(1, 6))

thread.start()
thread.join()
```

#### Example 3: Using Multiple Threads
```python
def print_even():
    for i in range(2, 11, 2):
        print(f"Even: {i}")

def print_odd():
    for i in range(1, 10, 2):
        print(f"Odd: {i}")

even_thread = threading.Thread(target=print_even)
odd_thread = threading.Thread(target=print_odd)

even_thread.start()
odd_thread.start()

even_thread.join()
odd_thread.join()
```

#### Example 4: Daemon Threads
Daemon threads are killed when the main program exits. They are useful for background tasks.

```python
def background_task():
    while True:
        print("Background task running...")

daemon_thread = threading.Thread(target=background_task)
daemon_thread.setDaemon(True)

daemon_thread.start()

# Main program will exit after some operation, killing the daemon thread
input("Press Enter to exit...\n")
```

#### Example 5: Thread Synchronization with Lock
To avoid race conditions, threads can be synchronized using a Lock.

```python
lock = threading.Lock()

def print_synced(num):
    lock.acquire()
    try:
        print(f"Printed by thread {num}")
    finally:
        lock.release()

threads = [threading.Thread(target=print_synced, args=(i,)) for i in range(5)]

for t in threads:
    t.start()

for t in threads:
    t.join()
```

These examples cover basic thread creation, argument passing, daemon threads, and synchronization. I'll provide the next set of examples in the following response. Let me know if you have any specific requests or questions about these examples!
