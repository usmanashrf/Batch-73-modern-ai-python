# More in Strings

## String Operators

### 1. String Concatenation (`+`)
`+` operator is used to concatenate two strings.

```python
str1 = "Hello"
str2 = "World"
result = str1 + " " + str2
print(result)  # Output: "Hello World"
```

### 2. Repetition (`*`)
The `*` operator is used to repeat a string a specified number of times.
```python
str1 = "Hello"
result = str1 * 3
print(result)  # Output: "HelloHelloHello"
```

### 3. Membership (`in`, `not in`)

#### 3a. Membership Operators 

The `in` and `not in` operators are used to check whether a substring exists within a string.
```python
str1 = "Hello World"
print("Hello" in str1)    # Output: True
print("Python" not in str1)  # Output: True
```

### 4. String Length (`len()`)
The `len()` function is used to get the length of a string.
```python
str1 = "Hello World"
print(len(str1))  # Output: 11
```

### 5. Indexing (`[]`)
Indexing allows to access individual characters in a string using their position.
```python
str1 = "Hello"
print(str1[0])  # Output: "H"
print(str1[-1]) # Output: "o"
```

### 6. Slicing (`[start:stop:step]`)
Slicing allows  to select a range of characters in a string.
```python
str1 = "Hello World"
print(str1[0:5])  # Output: "Hello"
print(str1[6:11]) # Output: "World"
```

### 7. String Comparison (`==`, `!=`, `<`, `>`, `<=`, `>=`)
#### 7a. Comparison Operators
Compare two values and return a Boolean result (True or False).

Equal to: ==
Not equal to: !=
Greater than: >
Less than: <
Greater than or equal to: >=
Less than or equal to: <=

```python 
result_equal: bool = 5 == 5
result_not_equal: bool = 10 != 7
result_greater_than: bool = 8 > 3
result_less_than: bool = 6 < 9
result_greater_equal: bool = 5 >= 5
result_less_equal: bool = 3 <= 4
```

Strings can be compared using comparison operators.
```python
str1 = "Hello"
str2 = "World"
print(str1 == str2)  # Output: False
print(str1 != str2)  # Output: True
print(str1 < str2)   # Output: True (since "H" comes before "W" lexicographically)
```

### 8. String Formatting (`%`, `.format()`, `f-strings`)
Strings can be formatted using different methods.
```python
name = "Alice"
age = 30

# Using % operator
print("My name is %s and I am %d years old." % (name, age))  # Output: "My name is Alice and I am 30 years old."

# Using .format()
print("My name is {} and I am {} years old.".format(name, age))  # Output: "My name is Alice and I am 30 years old."

# Using f-strings (Python 3.6+)
print(f"My name is {name} and I am {age} years old.")  # Output: "My name is Alice and I am 30 years old."
```
#### 8a. Common format specifiers
1. `%s` (String Format Specifier):

    * `%`s is used as a placeholder for a string. It tells Python to insert the string representation of the corresponding variable into the position where `%s` appears in the string.
    In our example:
    * `%s` corresponds to the variable name, which has the value "Alice".
    * "My name is `%s`" becomes "My name is Alice".
2. `%d` (Integer Format Specifier):

    * `%d` is used as a placeholder for an integer. It tells Python to insert the integer value of the corresponding variable into the position where `%d` appears in the string.
    In our example:
    * `%d` corresponds to the variable age, which has the value 30.
    * "I am `%d` years old" becomes "I am 30 years old".
3. `%f` (Float Format Specifier)
    ```python
    pi = 3.14159
    formatted_string = "The value of pi is approximately %.2f" % pi
    print(formatted_string)  # Output: "The value of pi is approximately 3.14"
    ```

4. `%x` (Integers in Hexadecimal Format Specifier)
    ```python
    number = 255
    formatted_string = "The hexadecimal representation of %d is %x" % (number, number)
    print(formatted_string)  # Output: "The hexadecimal representation of 255 is ff"
    ```

5. `%o` (Integers in Octal Format Specifier)

    ```python
    number = 255
    formatted_string = "The octal representation of %d is %o" % (number, number)
    print(formatted_string)  # Output: "The octal representation of 255 is 377"
    ```

6. `%e` (Scientific Format Specifier) e.g `2.5e+02`
    ```python
    large_number = 25000
    formatted_string = "The scientific notation of %d is %e" % (large_number, large_number)
    print(formatted_string)  # Output: "The scientific notation of 25000 is 2.500000e+04"
    ```

7. `%c` (Character Format Specifier)

    ```python
    char_code = 65
    formatted_string = "The character for ASCII code %d is %c" % (char_code, char_code)
    print(formatted_string)  # Output: "The character for ASCII code 65 is A"
    ```
8. `%r` (Raw Format Specifier)
    ```python
    text = "Hello\nWorld"
    formatted_string = "Raw representation: %r" % text
    print(formatted_string)  # Output: "Raw representation: 'Hello\\nWorld'"
    ```
### 9. Escape Sequence
- ```\  ``` -> Escape character
- ```\n ``` -> Escape sequence
- ```\n ``` -> inserts new line
- ```\\ ``` -> inserts backslach
- ```\' ``` -> inserts single quote
- ```\" ``` -> inserts double quote
- ```\t ``` -> inserts tab
- ```\r ``` -> moves the cursor to the start of the line
- ```\a ``` -> Beeps
- ```\b ``` -> Backspace

```python
print("Python Programming in \"PIAIC\"")
print("Python Programming in \\PIAIC")
print("Python Programming in \nPIAIC")
print("Python Programming in \tPIAIC")
print("Python Programming in PIAIC\rpiaic")
print("Python Programming in a\bPIAIC")
print("Python Programming in \aPIAIC")
```

### 10. Assignment Operators:

Assign values to variables and perform operations in a concise way.

Assignment: =
Addition assignment: +=
Subtraction assignment: -=
Multiplication assignment: *=
Division assignment: /=
Modulus assignment: %=
Floor division assignment: //=
Exponentiation assignment: **=

```python
x: int = 5
x += 3  # Equivalent to x = x + 3
y: float = 10
y /= 2  # Equivalent to y = y / 2
```

### 11. Comments.

In Python, comments are lines of text in your code that are not executed as part of the program. They are meant for human readers to understand the code better. Python supports two types of comments: single-line comments and multi-line comments.

#### 1. Single-line Comment

Single-line comments start with the # symbol and continue to the end of the line. Everything after # on that line is considered a comment and is ignored by the Python interpreter.


```python
# This is a single-line comment

print("Hello, World!")  # This is also a comment

Provides a brief comment on a single line.
```

#### 2. Multi-line Comments:

While Python doesn't have a built-in syntax for multi-line comments, you can use triple-quotes (''' or """) to create a multi-line string, and it's often used as a way to add multi-line comments. Although it's not ignored like a traditional comment, it serves the purpose of commenting out multiple lines.

```python
'''
This is a multi-line comment
spanning multiple lines.
'''
print("Hello, World!")

Demonstrates a comment spanning multiple lines.
```

### 12. Type conversion
This is the process of changing the data type of a value. Python provides functions like int(), float(), and complex() for type conversion.


```python
float_value: float = 3.75
int_value: int = 2

float_to_int: int = int(float_value)
int_to_float: float = float(int_value)

Illustrates converting between data types. 
```

### 13. `type`, `dir`, `id` functions
- `type` provides the type of a variable
- `dir` provides the list of attributes and methods of a variable
- `id` provides the memory address of a variable

```python
w = True
x = 5
y = 3.0
z = "Hello"

print(type(w)) 
print(type(x))  
print(type(y))  
print(type(z))  

print(dir(w))  
print(dir(x)) 
print(dir(y))
print(dir(z))

print(id(w))  
print(id(x)) 
print(id(y))
print(id(z))
```

### 14. Mutable and Immutable data types
Mutable data types are those that can be changed after they are created. Immutable data types are those that cannot be changed after they are created.

- Immutable data types: `int`, `float`, `str`, `bool`
- Mutable data types: `list`, `set`, `dict`

- If you want to store multiple items, you would need to create a separate variable for each one.

```
student1 = "Rehan"
student2 = "Muzhar"
student3 = "Ibtisam"
```

This approach works fine if you have just a few items. But what if you have 10, 100, or even more? It quickly becomes unmanageable.

- If you want to add or remove an item, you have to manually shift the data around or create new variables.

```
student4 = "Usman"
```

- Accessing an item requires you to remember the exact variable name associated with it.

```
print(student1)
print(student2)
```

# What is List?

A list in Python is like a container that can hold multiple items, one after another. Imagine you have a shopping list where you write down everything you need to buy. A Python list is very similar, but instead of just groceries, it can hold all kinds of things like numbers, words, or even other lists!

### Store Multiple Items Together:

A list allows you to keep multiple items in one place. For example, if you want to keep track of all your students' names, you can store them in a list.

```
students = ["Rehan", "Muzhar", "Ibtisam"]
```

### Access Items by Position:

Lists keep items in the order you put them in. You can access any item by telling Python where it is in the list (starting from 0).

```
print(students[0])
print(students[1])
```

### Change Items:

You can easily change an item in the list if you need to update it.

```
students[0] = "Ahmad"
```

### Adding or Removing elements from list

```
students = ["Rehan", "Muzhar", "Ibtisam"]

# Append a new student
students.append("Usman")
print(students)  # Output: ["Rehan", "Muzhar", "Ibtisam", "Usman"]

# Pop the last student
last_student = students.pop()
print(last_student)  # Output: "Usman"
print(students)      # Output: ["Rehan", "Muzhar", "Ibtisam"]

# Remove a specific student by name
students.remove("Rehan")
print(students)  # Output: ["Muzhar", "Ibtisam"]



# Initial list of students
students: list[str] = ["Rehan", "Muzhar", "Ibtisam"]

# New students to be added
new_students: list[str] = ["Usman", "Ahmed"]

# Extend the original students list with the new students
students.extend(new_students)

```

---

## Indexing

Indexing is how you access individual elements in a list using their position in the list. In Python, lists are zero-indexed, meaning that the first element in a list is at index 0, the second element is at index 1, and so on.

```
               0        1          2
students = ["Rehan", "Muzhar", "Ibtisam"]   # length-1 
             -3         -2        -1
```

## Slicing with Indexes

```
phrase = list("LongLivePakistan!")

```

#### Positive Indexing

```
part1 = phrase[0:4]
print(part1)  # Output: "Long"


part2 = phrase[4:8]
print(part2)  # Output: "Live"


part3 = phrase[8:16]
print(part3)  # Output: "Pakistan"

```

#### Negative Indexing

```
part4 = phrase[-9:-1]
print(part4)  # Output: "Pakistan"


part5 = phrase[-14:-10]
print(part5)  # Output: "Live"


part6 = phrase[:-1]
print(part6)  # Output: "LongLivePakistan"

```

#### Slicing with Steps

```
part7 = phrase[::2]
print(part7)  # Output: "LnLvPksa!"



part8 = phrase[0:8:2]
print(part8)  # Output: "LnLv"

```

Reversing the entire string
```
reversed_phrase = phrase[::-1]
print(reversed_phrase)  # Output: "!natsikaPevignoL"
```

Combining Positive and Negative Indexing with Steps
 
```
part10 = phrase[6:-2:2]
print(part10)  # Output: "vekaP"
```


## Some interesting concepts in Lists

```python

zero_list = [0] * 5
print(zero_list)  # Output: [0, 0, 0, 0, 0]

# list concatenation
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined_list = list1 + list2
print(combined_list)  # Output: [1, 2, 3, 4, 5, 6]

# list repetition
repeated_list = list1 * 3
print(repeated_list)  # Output: [1, 2, 3, 1, 2, 3, 1, 2, 3]

# list membership
a = 1 in list1
print(a)  # Output: True

b = 7 in list1
print(b)  # Output: False

# list length
length = len(list1)
print(length)  # Output: 3

# list and range function
new_list = list(range(10))
print(new_list)  # Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

message = "Hello, World!"
characters = list(message)
print(characters)  # Output: ['H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd', '!']

# list unpacking
numbered_list = [4, 8, 6]
a, b, c = numbered_list
print(a)  # Output: 4
print(b)  # Output: 8
print(c)  # Output: 6

another_list = [1,2,3,4,5,6,7,8,9,10]
x, *y, z = another_list
print(x)  # Output: 1
print(y)  # Output: [2, 3, 4, 5, 6, 7, 8]
print(z)  # Output: 10
```


