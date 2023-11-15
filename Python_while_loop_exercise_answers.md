Python While Loop Exercises
1. Print numbers from 1 to 10 using a while loop:
   ```python
   num = 1
   while num <= 10:
       print(num)
       num += 1
   ```

2. Calculate the sum of numbers from 1 to 100 using a while loop:
   ```python
   num = 1
   total = 0
   while num <= 100:
       total += num
       num += 1
   print("Sum:", total)
   ```

3. Find the factorial of a given number using a while loop:
   ```python
   num = 5
   factorial = 1
   while num > 0:
       factorial *= num
       num -= 1
   print("Factorial:", factorial)
   ```

4. Print the Fibonacci series up to a certain limit using a while loop:
   ```python
   limit = 10
   a, b = 0, 1
   count = 0
   while count < limit:
       print(a, end=' ')
       a, b = b, a + b
       count += 1
   ```

5. Check if a given number is prime using a while loop:
   ```python
   num = 17
   is_prime = True
   divisor = 2
   while divisor <= num // 2:
       if num % divisor == 0:
           is_prime = False
           break
       divisor += 1
   print("Is prime?", is_prime)
   ```

6. Find the reverse of a number using a while loop:
   ```python
   num = 12345
   reversed_num = 0
   while num > 0:
       digit = num % 10
       reversed_num = reversed_num * 10 + digit
       num //= 10
   print("Reversed number:", reversed_num)
   ```

7. Calculate the square root of a number using the Newton-Raphson method and a while loop:
   ```python
   num = 25
   guess = num / 2
   while abs(guess * guess - num) > 1e-5:
       guess = (guess + num / guess) / 2
   print("Square root:", guess)
   ```

8. Print a pattern of asterisks in an ascending triangle using a while loop:
   ```python
   rows = 5
   row = 1
   while row <= rows:
       print('*' * row)
       row += 1
   ```

9. Print the multiplication table of a given number using a while loop:
   ```python
   num = 5
   multiplier = 1
   while multiplier <= 10:
       product = num * multiplier
       print(f"{num} x {multiplier} = {product}")
       multiplier += 1
   ```

10. Calculate the sum of digits in a given number using a while loop:
    ```python
    num = 12345
    total = 0
    while num > 0:
        digit = num % 10
        total += digit
        num //= 10
    print("Sum of digits:", total)
    ```

11. Check if a given string is a palindrome using a while loop:
    ```python
    string = "racecar"
    left = 0
    right = len(string) - 1
    is_palindrome = True
    while left < right:
        if string[left] != string[right]:
            is_palindrome = False
            break
        left += 1
        right -= 1
    print("Is palindrome?", is_palindrome)
    ```

12. Find the common elements between two lists using a while loop:
    ```python
    list1 = [1, 2, 3, 4, 5]
    list2 = [3, 4, 5, 6, 7]
    common_elements = []
    
    index1 = 0
    while index1 < len(list1):
        index2 = 0
        while index2 < len(list2):
            if list1[index1] == list2[index2]:
                common_elements.append(list1[index1])
            index2 += 1
        index1 += 1
    
    print("Common elements:", common_elements)

    ```

13. Generate a list of prime numbers up to a certain limit using a while loop:
    ```python
    def is_prime(n):
        if n <= 1:
            return False
        divisor = 2
        while divisor * divisor <= n:
            if n % divisor == 0:
                return False
            divisor += 1
        return True

    limit = 50
    primes = []
    num = 2
    while num <= limit:
        if is_prime(num):
            primes.append(num)
        num += 1
    print("Prime numbers up to", limit, ":", primes)
    ```

14. Print the ASCII values of all uppercase letters using a while loop:
    ```python
    letter = 'A'
    while letter <= 'Z':
        ascii_value = ord(letter)
        print(letter, ":", ascii_value)
        letter = chr(ord(letter) + 1)
    ```

15. Reverse a string using a while loop:
    ```python
    string = "Hello, World!"
    reversed_string = ""
    index = len(string) - 1
    while index >= 0:
        reversed_string += string[index]
        index -= 1
    print("Reversed string:", reversed_string)
    ```

16. Calculate the power of a number using a while loop (without using the exponentiation operator):
    ```python
    base = 2
    exponent = 5
    result = 1
    count = 0
    while count < exponent:
        result *= base
        count += 1
    print("Result:", result)
    ```

17. Find the GCD (Greatest Common Divisor) of two numbers using the Euclidean algorithm and a while loop:
    ```python
    def gcd(a, b):
        while b:
            a, b = b, a % b
        return a

    num1 = 36
    num2 = 48
    result = gcd(num1, num2)
    print("GCD of", num1, "and", num2, ":", result)
    ```

18. Count the number of vowels in a given string using a while loop:
    ```python
    string = "Hello, World!"
    vowels = "AEIOUaeiou"
    count = 0
    index = 0
    while index < len(string):
        if string[index] in vowels:
            count += 1
        index += 1
    print("Number of vowels:", count)
    ```

19. Count the number of words in a given sentence using a while loop:
    ```python
    sentence = "This is a sample sentence."
    words = 0
    index = 0
    while index < len(sentence):
        if sentence[index].isspace():
            words += 1
        index += 1
    words += 1  # Add 1 for the last word
    print("Number of words:", words)
    ```

20. Remove duplicates from a list using a while loop:
    ```python
    numbers = [1, 2, 2, 3, 4, 4, 5]
    unique_numbers = []
    index = 0
    while index < len(numbers):
        if numbers[index] not in unique_numbers:
            unique_numbers.append(numbers[index])
        index += 1
    print("List with duplicates removed:", unique_numbers)
    ```

21. Calculate the mean (average) of a list of numbers using a while loop:
    ```python
    numbers = [10, 20, 30, 40, 50]
    total = 0
    count = 0
    while count < len(numbers):
        total += numbers[count]
        count += 1
    mean = total / len(numbers)
    print("Mean (average):", mean)
    ```

22. Calculate the median of a list of numbers using a while loop:
    ```python
    numbers = [10, 20, 30, 40, 50]
    numbers.sort()
    middle = len(numbers) // 2
    if len(numbers) % 2 == 0:
        median = (numbers[middle - 1] + numbers[middle]) / 2
    else:
        median = numbers[middle]
    print("Median:", median)
    ```

23. Calculate the standard deviation of a list of numbers using a while loop:
    ```python
    import math

    numbers = [10, 20, 30, 40, 50]
    mean = sum(numbers) / len(numbers)
    squared_diff = 0
    count = 0
    while count < len(numbers):
        squared_diff += (numbers[count] - mean) ** 2
        count += 1
    variance = squared_diff / len(numbers)
    std_deviation = math.sqrt(variance)
    print("Standard Deviation:", std_deviation)
    ```

24. Implement a simple calculator that can perform addition, subtraction, multiplication, and division using a while loop:
    ```python
    while True:
        print("Options:")
        print("Enter 'add' for addition")
        print("Enter 'sub' for subtraction")
        print("Enter 'mul' for multiplication")
        print("Enter 'div' for division")
        print("Enter 'quit' to end the program")
        user_input = input(": ")

        if user_input == "quit":
            break
        elif user_input in ("add", "sub", "mul", "div"):
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))
            if user_input == "add":
                result = num1 + num2
            elif user_input == "sub":
                result = num1 - num2
            elif user_input == "mul":
                result = num1 * num2
            elif user_input == "div":
                result = num1 / num2
            print("Result:", result)
        else:
            print("Invalid input")
    ```

25. Simulate a guessing game where the user has to guess a random number within a given range using a while loop:
    ```python
    import random

    lower = 1
    upper = 100
    target = random.randint(lower, upper)
    attempts = 0

    while True:
        guess = int(input(f"Guess the number between {lower} and {upper}: "))
        attempts += 1
        if guess < target:
            print("Too low!")
        elif guess > target:
            print("Too high!")
        else:
            print(f"Congratulations! You guessed it in {attempts} attempts.")
            break
    ```

