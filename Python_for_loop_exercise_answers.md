For Loop Exercise Answers

1. Print numbers from 1 to 10:
   ```python
   for num in range(1, 11):
       print(num)
   ```

2. Print even numbers from 1 to 20:
   ```python
   for num in range(2, 21, 2):
       print(num)
   ```

3. Print the multiplication table of a given number (e.g., 5):
   ```python
   num = 5
   for i in range(1, 11):
       print(num, 'x', i, '=', num * i)
   ```

4. Calculate the sum of numbers from 1 to 100:
   ```python
   total = 0
   for num in range(1, 101):
       total += num
   print("Sum:", total)
   ```

5. Find the factorial of a given number (e.g., 5):
   ```python
   num = 5
   factorial = 1
   for i in range(1, num + 1):
       factorial *= i
   print("Factorial:", factorial)
   ```

6. Print the Fibonacci series up to a certain limit (e.g., 10 terms):
   ```python
   limit = 10
   a, b = 0, 1
   for _ in range(limit):
       print(a, end=' ')
       a, b = b, a + b
   ```

7. Find the sum of all prime numbers between 1 and 50:
   ```python
   def is_prime(n):
       if n <= 1:
           return False
       for i in range(2, int(n**0.5) + 1):
           if n % i == 0:
               return False
       return True

   total = 0
   for num in range(1, 51):
       if is_prime(num):
           total += num
   print("Sum of prime numbers:", total)
   ```

8. Count the number of vowels in a given string (e.g., "Hello, World!"):
   ```python
   string = "Hello, World!"
   vowels = "AEIOUaeiou"
   count = 0
   for char in string:
       if char in vowels:
           count += 1
   print("Number of vowels:", count)
   ```

9. Count the number of words in a given sentence (e.g., "This is a sample sentence."):
   ```python
   sentence = "This is a sample sentence."
   words = len(sentence.split())
   print("Number of words:", words)
   ```

10. Reverse a string (e.g., "Hello, World!"):
    ```python
    string = "Hello, World!"
    reversed_string = string[::-1]
    print("Reversed string:", reversed_string)
    ```

11. Find the largest element in a list of numbers:
    ```python
    numbers = [12, 45, 23, 67, 89, 34]
    largest = max(numbers)
    print("Largest element:", largest)
    ```

12. Find the smallest element in a list of numbers:
    ```python
    numbers = [12, 45, 23, 67, 89, 34]
    smallest = min(numbers)
    print("Smallest element:", smallest)
    ```

13. Check if all elements in a list are even:
    ```python
    numbers = [2, 4, 6, 8, 10]
    all_even = all(num % 2 == 0 for num in numbers)
    print("All elements are even?", all_even)
    ```

14. Check if a given string is a palindrome (e.g., "racecar"):
    ```python
    string = "racecar"
    is_palindrome = string == string[::-1]
    print("Is it a palindrome?", is_palindrome)
    ```

15. Find the common elements between two lists:
    ```python
    list1 = [1, 2, 3, 4, 5]
    list2 = [3, 4, 5, 6, 7]
    common_elements = [elem for elem in list1 if elem in list2]
    print("Common elements:", common_elements)
    ```

16. Remove duplicates from a list:
    ```python
    numbers = [1, 2, 2, 3, 4, 4, 5]
    unique_numbers = list(set(numbers))
    print("List with duplicates removed:", unique_numbers)
    ```

17. Find the square of each element in a list:
    ```python
    numbers = [1, 2, 3, 4, 5]
    squares = [num ** 2 for num in numbers]
    print("Squares of elements:", squares)
    ```

18. Print a pattern of asterisks (e.g., 5 rows of asterisks):
    ```python
    rows = 5
    for i in range(1, rows + 1):
        print("*" * i)
    ```

19. Calculate the sum of digits in a given number (e.g., 12345):
    ```python
    num = 12345
    total = sum(int(digit) for digit in str(num))
    print("Sum of digits:", total)
    ```

20. Find the GCD (Greatest Common Divisor) of two numbers (e.g., 36 and 48):
    ```python
    import math

    num1 = 36
    num2 = 48
    gcd = math.gcd(num1, num2)
    print("GCD of {} and {}: {}".format(num1, num2, gcd))
    ```

21. Print the ASCII values of all uppercase letters:
    ```python
    for char in range(ord('A'), ord('Z') + 1):
        print(chr(char), ":", char)
    ```

22. Generate a list of prime numbers up to a certain limit (e.g., up to 50):
    ```python
    def is_prime(n):
        if n <= 1:
            return False
        for i in range(2, int(n**0.5) + 1):
            if n % i == 0:
                return False
        return True

    limit = 50
    primes = [num for num in range(2, limit + 1) if is_prime(num)]
    print("Prime numbers up to {}: {}".format(limit, primes))
    ```

23. Find the number of occurrences of a specific element in a list (e.g., count of 3 in [1, 2, 3, 3, 4, 3]):
    ```python
    numbers = [1, 2, 3, 3, 4, 3]
    count = numbers.count(3)
    print("Occurrences of 3:", count)
    ```

24. Calculate the power of a number using the exponentiation operator (e.g., 2^5):
   ```python
   base = 2
   exponent = 5
   result = base ** exponent
   print("Result:", result)
   ```

25. Generate the first 'n' terms of the geometric series (e.g., first 5 terms of 2^0, 2^1, 2^2, ...):
   ```python
   n = 5
   base = 2
   geometric_series = [base ** i for i in range(n)]
   print("Geometric series:", geometric_series)
   ```
