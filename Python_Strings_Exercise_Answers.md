Here are the solutions to the 20 Python string exercises:

1. **Length of a String:**
   ```python
   string = "Hello, World!"
   length = len(string)
   print("Length of the string:", length)
   ```

2. **Count Characters in a String:**
   ```python
   string = "Hello, World!"
   count = len([char for char in string if char.isalnum()])
   print("Number of characters in the string:", count)
   ```

3. **Count Words in a String:**
   ```python
   string = "This is a sample sentence."
   words = len(string.split())
   print("Number of words in the string:", words)
   ```

4. **Reverse a String:**
   ```python
   string = "Hello, World!"
   reversed_string = string[::-1]
   print("Reversed string:", reversed_string)
   ```

5. **Check for Palindrome:**
   ```python
   string = "racecar"
   is_palindrome = string == string[::-1]
   print("Is it a palindrome?", is_palindrome)
   ```

6. **Capitalize First Letter of Each Word:**
   ```python
   string = "hello world"
   capitalized_string = string.title()
   print("Capitalized string:", capitalized_string)
   ```

7. **Convert to Lowercase:**
   ```python
   string = "Hello, World!"
   lowercase_string = string.lower()
   print("Lowercase string:", lowercase_string)
   ```

8. **Remove Whitespace from Ends:**
   ```python
   string = "   Trim me!   "
   trimmed_string = string.strip()
   print("Trimmed string:", trimmed_string)
   ```

9. **Find Substring Index:**
   ```python
   string = "Hello, World!"
   substring = "World"
   index = string.find(substring)
   print("Index of '{}' in the string: {}".format(substring, index))
   ```

10. **Replace Substring:**
    ```python
    string = "Hello, World!"
    new_string = string.replace("World", "Python")
    print("Modified string:", new_string)
    ```

11. **Split String into Words:**
    ```python
    string = "This is a sample sentence."
    words = string.split()
    print("Words in the string:", words)
    ```

12. **Join Words into String:**
    ```python
    words = ["This", "is", "a", "sample", "sentence."]
    string = " ".join(words)
    print("Joined string:", string)
    ```

13. **Remove Digits from String:**
    ```python
    string = "Hello123"
    without_digits = ''.join([char for char in string if not char.isdigit()])
    print("String without digits:", without_digits)
    ```

14. **Count Specific Character:**
    ```python
    string = "Hello, World!"
    char_to_count = ","
    count = string.count(char_to_count)
    print("Occurrences of '{}': {}".format(char_to_count, count))
    ```

15. **Remove Punctuation from String:**
    ```python
    import string

    string_with_punctuation = "Hello, World!"
    translator = str.maketrans('', '', string.punctuation)
    no_punctuation_string = string_with_punctuation.translate(translator)
    print("String without punctuation:", no_punctuation_string)
    ```

16. **Check for Digits Only:**
    ```python
    string = "12345"
    is_digits_only = string.isdigit()
    print("Contains only digits?", is_digits_only)
    ```

17. **Check for Alphabetic Characters Only:**
    ```python
    string = "Hello"
    is_alpha_only = string.isalpha()
    print("Contains only alphabetic characters?", is_alpha_only)
    ```

18. **Find Longest Word:**
    ```python
    string = "This is a sample sentence."
    words = string.split()
    longest_word = max(words, key=len)
    print("Longest word:", longest_word)
    ```

19. **Reverse Order of Words:**
    ```python
    string = "This is a sample sentence."
    words = string.split()
    reversed_string = " ".join(reversed(words))
    print("Reversed order of words:", reversed_string)
    ```

20. **Check for Anagrams:**
    ```python
    def is_anagram(str1, str2):
        return sorted(str1) == sorted(str2)

    string1 = "listen"
    string2 = "silent"
    result = is_anagram(string1, string2)
    print("Are '{}' and '{}' anagrams?".format(string1, string2), result)
    ```
