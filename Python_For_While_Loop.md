
**Project 3: Simple Calculator (Using `while` Loop)**
```python
# Simple Calculator
while True:
    print("Options:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Quit")
    
    choice = input("Enter your choice (1/2/3/4/5): ")
    
    if choice == '5':
        print("Goodbye!")
        break
    
    if choice in ('1', '2', '3', '4'):
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        
        if choice == '1':
            result = num1 + num2
        elif choice == '2':
            result = num1 - num2
        elif choice == '3':
            result = num1 * num2
        elif choice == '4':
            if num2 != 0:
                result = num1 / num2
            else:
                print("Division by zero is not allowed.")
                continue
        
        print(f"Result: {result}")
    else:
        print("Invalid choice. Please choose a valid option.")
```

**Project 4: Dice Rolling Simulator (Using `for` Loop)**
```python
import random

# Dice Rolling Simulator
def roll_dice():
    return random.randint(1, 6)

num_rolls = int(input("Enter the number of times to roll the dice: "))

for _ in range(num_rolls):
    result = roll_dice()
    print(f"You rolled a {result}")

print("Thanks for playing!")
```

**Project 5: Password Generator (Using `while` Loop)**
```python
import random
import string

# Password Generator
while True:
    length = int(input("Enter the length of the password (at least 6 characters): "))
    
    if length < 6:
        print("Password length should be at least 6 characters.")
        continue
    
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    
    print(f"Generated password: {password}")
    
    regenerate = input("Do you want to generate another password? (yes/no): ")
    if regenerate.lower() != 'yes':
        break
```


**Project 1: Simple To-Do List (Using `while` Loop)**
```python
# Simple To-Do List
todo_list = []

while True:
    print("\nOptions:")
    print("1. Add a task")
    print("2. Remove a task")
    print("3. View tasks")
    print("4. Quit")
    
    choice = input("Enter your choice: ")
    
    if choice == '1':
        task = input("Enter a task: ")
        todo_list.append(task)
        print("Task added successfully!")
    elif choice == '2':
        if len(todo_list) == 0:
            print("The to-do list is empty.")
        else:
            print("Tasks:")
            for index, task in enumerate(todo_list):
                print(f"{index + 1}. {task}")
            task_index = int(input("Enter the task number to remove: ")) - 1
            if task_index >= 0 and task_index < len(todo_list):
                removed_task = todo_list.pop(task_index)
                print(f"Removed task: {removed_task}")
            else:
                print("Invalid task number.")
    elif choice == '3':
        if len(todo_list) == 0:
            print("The to-do list is empty.")
        else:
            print("Tasks:")
            for index, task in enumerate(todo_list):
                print(f"{index + 1}. {task}")
    elif choice == '4':
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please choose a valid option.")
```

**Project 2: Number Guessing Game (Using `for` Loop)**
```python
import random

# Number Guessing Game
target_number = random.randint(1, 100)
attempts = 0

print("Welcome to the Number Guessing Game!")
print("I'm thinking of a number between 1 and 100.")

for attempt in range(1, 11):
    guess = int(input(f"Attempt {attempt}: Enter your guess: "))
    
    if guess < target_number:
        print("Too low! Try a higher number.")
    elif guess > target_number:
        print("Too high! Try a lower number.")
    else:
        print(f"Congratulations! You guessed the number ({target_number}) in {attempt} attempts.")
        break
else:
    print(f"Sorry, you've used all your attempts. The number was {target_number}.")
```



**Python `for` Loop Tutorials with Examples:**

1. **Basic `for` Loop:**
   ```python
   for i in range(5):
       print(i)
   ```

2. **Looping through a List:**
   ```python
   fruits = ["apple", "banana", "cherry"]
   for fruit in fruits:
       print(fruit)
   ```

3. **Iterating Over a String:**
   ```python
   sentence = "Hello, World!"
   for char in sentence:
       print(char)
   ```

4. **Looping with a Step Value:**
   ```python
   for i in range(0, 10, 2):
       print(i)
   ```

5. **Using `enumerate` for Index and Value:**
   ```python
   colors = ["red", "green", "blue"]
   for index, color in enumerate(colors):
       print(f"Color {index + 1}: {color}")
   ```

6. **Looping through a Dictionary:**
   ```python
   user_info = {"name": "Alice", "age": 30, "city": "Chennai"}
   for key, value in user_info.items():
       print(f"{key}: {value}")
   ```

7. **Nested `for` Loops:**
   ```python
   for i in range(3):
       for j in range(2):
           print(f"({i}, {j})")
   ```

8. **Looping with a Break Statement:**
   ```python
   for i in range(10):
       if i == 5:
           break
       print(i)
   ```

9. **Looping with a Continue Statement:**
   ```python
   for i in range(5):
       if i == 2:
           continue
       print(i)
   ```

10. **Using `else` with `for` Loop:**
    ```python
    for i in range(5):
        print(i)
    else:
        print("Loop finished without a break")
    ```

**Python `while` Loop Tutorials with Examples:**

1. **Basic `while` Loop:**
   ```python
   count = 0
   while count < 5:
       print(count)
       count += 1
   ```

2. **Loop with User Input Validation:**
   ```python
   while True:
       user_input = input("Enter 'q' to quit: ")
       if user_input == 'q':
           break
   ```

3. **Using `else` with `while` Loop:**
   ```python
   count = 0
   while count < 5:
       print(count)
       count += 1
   else:
       print("Loop finished without a break")
   ```

4. **Infinite Loop with `while` and `break`:**
   ```python
   while True:
       print("This is an infinite loop. Press 'q' to exit.")
       user_input = input()
       if user_input == 'q':
           break
   ```

5. **Looping with a Conditional `continue`:**
   ```python
   count = 0
   while count < 5:
       count += 1
       if count == 2:
           continue
       print(count)
   ```

6. **Using a `while` Loop for Web Scraping:**
   ```python
   import requests
   while True:
       response = requests.get("https://example.com")
       if response.status_code == 200:
           print("Web page fetched successfully.")
           break
       else:
           print("Failed to fetch the web page. Retrying...")
   ```

7. **Loop with a Timeout:**
   ```python
   import time
   timeout = 10  # Timeout in seconds
   start_time = time.time()
   while True:
       if time.time() - start_time > timeout:
           print("Timeout reached.")
           break
       else:
           print("Waiting...")
           time.sleep(1)
   ```

8. **Looping until a Condition is Met:**
   ```python
   total = 0
   while total < 100:
       total += int(input("Enter a number: "))
   ```

9. **Using `while` for Dynamic Web Content Loading:**
   ```python
   while True:
       # Check if a specific element is visible on a web page
       if is_element_visible("some_element_id"):
           print("Element found!")
           break
       else:
           print("Element not found. Waiting...")
           time.sleep(2)
   ```

10. **Loop with Error Handling for Web API Requests:**
    ```python
    import requests
    max_attempts = 3
    attempts = 0
    while attempts < max_attempts:
        try:
            response = requests.get("https://api.example.com/data")
            response.raise_for_status()
            data = response.json()
            print("Data fetched successfully.")
            break
        except Exception as e:
            print(f"Error: {str(e)}")
            attempts += 1
            if attempts < max_attempts:
                print("Retrying...")
            else:
                print("Max attempts reached.")
                break
    ```

