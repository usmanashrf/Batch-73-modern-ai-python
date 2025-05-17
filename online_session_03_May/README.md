# Introduction to Tuples in Python
A sequence is a type of data in python which is able to store more than one value. These values can be sequentially browsed i.e. element by element. 

So far, we've only studied one type of sequence i.e. `list`. Here we'll explore another type of sequene called `tuple`. 

We've already discussed the concept of **Immutability** and **Mutability**. Let's revise it. 

- *Immutabale* means can't be changed/modified/updated. Example: Primitive Data types
- *Mutable* means can be changed/modified/updated. Example: Lists in Python


## What is a Tuple?

A tuple is an immutable, ordered collection of elements in Python. Like lists, tuples can hold a sequence of elements, but unlike lists, tuples cannot be changed (i.e., modified) after they are created. Tuples are typically used to group together related data.

## Why Do We Need Tuples?
### The Problem: Need for Immutable Collections

In programming, there are situations where we want to ensure that a sequence of values remains constant throughout the program. For example, we might have a set of coordinates or configuration values that should not be altered accidentally.

Using a list for such cases is risky because lists are mutable, meaning their content can be changed. This is where tuples come in handy.

### The Solution: Using Tuples for Immutable Sequences

Tuples provide a way to create a sequence of elements that cannot be modified. This immutability makes tuples useful in scenarios where the integrity of the data must be preserved.

```python
coordinates : tuple[int,int] = (10, 20)
print(coordinates)  # Output: (10, 20)

# Trying to modify a tuple will raise an error
# coordinates[0] = 15  # This will raise a TypeError
```

## How Tuples Work

### Basic Syntax

Tuples are created by placing a sequence of elements separated by commas within parentheses:

```python
my_tuple : tuple[int, int, int] = (1, 2, 3)
```

### Example: Storing Multiple Values

Tuples can be used to store related data, such as the x, y, and z coordinates of a point in space:

```python
point : tuple[int, int, int] = (1, 2, 3)
print(point)  # Output: (1, 2, 3)
```

### Creating a Tuple Without Parentheses

We can also create a tuple without using parentheses by simply separating the elements with commas:

```python
my_tuple : tuple[int, int, int] = 1, 2, 3
print(my_tuple)  # Output: (1, 2, 3)
```

### Single-Element Tuples

To create a tuple with a single element, we must include a trailing comma:

```python
single_element_tuple = (5,)
print(single_element_tuple)  # Output: (5,)
```

Without the comma, Python will not recognize it as a tuple:

```python
not_a_tuple = (5)
print(type(not_a_tuple))  # Output: <class 'int'>
```

## Operations with Tuples

### Accessing Elements

We can access elements in a tuple using indexing, similar to lists:

```python
my_tuple = ('apple', 'banana', 'cherry')
print(my_tuple[1])  # Output: banana
```

### Slicing Tuples

We can slice tuples to get a range of elements:

```python
my_tuple = ('apple', 'banana', 'cherry', 'date')
print(my_tuple[1:3])  # Output: ('banana', 'cherry')
```

### Tuple Concatenation and Repetition

Tuples can be concatenated using the `+` operator and repeated using the `*` operator:

```python
# Concatenation
tuple1 = (1, 2)
tuple2 = (3, 4)
result = tuple1 + tuple2
print(result)  # Output: (1, 2, 3, 4)

# Repetition
repeated_tuple = ('A',) * 3
print(repeated_tuple)  # Output: ('A', 'A', 'A')
```

### Tuple Unpacking

Tuple unpacking allows us to assign each element of a tuple to a variable in a single statement:

```python
scores = (10, 20)
x, y = scores
print(x)  # Output: 10
print(y)  # Output: 20
```

### Nesting Tuples

Tuples can contain other tuples, which is useful for organizing data hierarchically:

```python
nested_tuple = (1, (2, 3), (4, 5, 6))
print(nested_tuple)  # Output: (1, (2, 3), (4, 5, 6))
```

## Advantages of Tuples

### 1. Immutability

The immutability of tuples ensures that the data remains consistent and secure, especially in cases where the data should not be altered.

### 2. Performance

Tuples are generally faster than lists for iterating through elements because they are immutable and therefore require less memory.

### 3. Use as Dictionary Keys

Because tuples are immutable, they can be used as keys in dictionaries, unlike lists.

```python
location = {}
point = (10, 20)
location[point] = "Park"
print(location)  # Output: {(10, 20): 'Park'}
```

## Conclusion

Tuples are a fundamental data structure in Python that provide a way to store ordered, immutable collections of elements. They are ideal for situations where we need a sequence of elements that should not be changed, and they offer several advantages in terms of performance and data integrity.


## Tuple Methods and Operations

### 1. `count()`

The `count()` method returns the number of occurrences of a specified value in the tuple.

#### Example:

```python
my_tuple = (1, 2, 3, 2, 2, 4)
count_of_twos = my_tuple.count(2)
print(count_of_twos)  # Output: 3
```

### 2. `index()`

The `index()` method returns the index of the first occurrence of a specified value. If the value is not found, it raises a `ValueError`.

#### Example:

```python
my_tuple = ('apple', 'banana', 'cherry')
index_of_banana = my_tuple.index('banana')
print(index_of_banana)  # Output: 1
```

### Tuple Operations

#### 1. Accessing Elements

We can access elements of a tuple using square brackets `[]` with the index of the element. Remember that tuple indices start at 0.

```python
my_tuple = ('apple', 'banana', 'cherry')
print(my_tuple[0])  # Output: apple
```

#### 2. Slicing

We can slice a tuple to get a subset of elements:

```python
my_tuple = ('apple', 'banana', 'cherry', 'date')
print(my_tuple[1:3])  # Output: ('banana', 'cherry')
```

#### 3. Concatenation

Tuples can be concatenated using the `+` operator:

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
result = tuple1 + tuple2
print(result)  # Output: (1, 2, 3, 4, 5, 6)
```

#### 4. Repetition

We can repeat a tuple a certain number of times using the `*` operator:

```python
my_tuple = ('A', 'B')
repeated_tuple = my_tuple * 3
print(repeated_tuple)  # Output: ('A', 'B', 'A', 'B', 'A', 'B')
```

#### 5. Membership Test

We can check if an item exists in a tuple using the `in` keyword:

```python
my_tuple = ('apple', 'banana', 'cherry')
print('banana' in my_tuple)  # Output: True
print('grape' in my_tuple)   # Output: False
```

#### 6. Iterating Over a Tuple

We can iterate over the elements of a tuple using a `for` loop:

```python
my_tuple = ('apple', 'banana', 'cherry')
for fruit in my_tuple:
    print(fruit)
# Output:
# apple
# banana
# cherry
```

### Tuple Usage Examples


#### 1. Swapping Variables

Tuples can be used for swapping the values of two variables without needing a temporary variable.

```python
a = 5
b = 10
a, b = b, a
print(a)  # Output: 10
print(b)  # Output: 5
```
#### 2. Swapping Tuples
Tuples themselves can be swapped.

```python
t1 = (1,2)
t2 = (2,3)
print(f"Before swapping: t1={t1} and t2={t2}") # Output: Before swapping: t1=(1, 2) and t2=(2, 3)
t1, t2 = t2, t1
print(f"After swapping: t1={t1} and t2={t2}") # Output: After swapping: t1=(2, 3) and t2=(1, 2)
```

#### 3. Storing Related Data

Tuples can store related data, like coordinates or RGB color values.

```python
point = (10, 20)
color = (255, 0, 0)

print(point)  # Output: (10, 20)
print(color)  # Output: (255, 0, 0)
```

#### 4. Using Tuples as Dictionary Keys

Because tuples are immutable, they can be used as keys in dictionaries.

```python
locations = {}
point = (10, 20)
locations[point] = "Park"
print(locations)  # Output: {(10, 20): 'Park'}
```


---
# Introduction to Dictionaries in Python

## What is a Dictionary?

Dictionary, a data structure in Python, is a collection of *key-value pairs*, where each *key is unique*, and each key is associated with a specific value. Unlike other data structures in Python, like lists or sets, *dictionaries are unordered*, meaning that the items are not stored in any particular sequence.

Dictionary enable the association of values with unique keys, providing a way to store and retrieve information using meaningful identifiers. Dictionaries are particularly valuable when there is a need for fast data access and retrieval based on specific keys. They are versatile and widely used in scenarios where data needs to be stored and accessed in a structured manner.

## Why Do We Need Dictionaries?

### The Problem: Efficient Data Lookups

Consider a scenario where 're managing a collection of student scores in different subjects. Initially,  might think of using two separate lists—one for student names and one for their corresponding scores:

```python
students : list[str ]= ["Alice", "Bob", "Charlie"]
scores : list[int] = [85, 92, 78]
```

To find the score of a specific student,  would need to first find the index of the student's name in the `students` list and then use that index to look up the score in the `scores` list:

```python
index : int = students.index("Alice")
score : int = scores[index]
```

While this approach works, it quickly becomes inefficient as the lists grow in size. Searching for a student's name in the list takes time, and managing two separate lists can lead to errors, especially if they become out of sync.

### The Solution: Constant-Time Lookups with Dictionaries

Dictionaries provide a more efficient and intuitive way to handle this situation. By using student names as keys and their scores as values,  can store the data in a dictionary:

```python
students_scores : dict{str,int} = {
    "Alice": 85,
    "Bob": 92,
    "Charlie": 78
}
```

Now, finding a student's score is much simpler and faster:

```python
score : int = students_scores["Alice"]
```

This operation is performed in constant time, regardless of the number of students.

## What Problems Do Dictionaries Solve?

### 1. Fast Data Retrieval

Dictionaries are optimized for fast data retrieval. Instead of searching through an entire list,  can quickly access any value directly by its key.

### 2. Clearer, More Expressive Code

Dictionaries allow us to write clearer and more expressive code. The key-value structure makes it obvious what each item represents, improving code readability.

### 3. Flexibility in Data Organization

Dictionaries offer flexibility in how  organize data.  can store complex structures, like lists or other dictionaries, as values, enabling us to represent nested or hierarchical data.

## Working with Dictionaries in Python

### Important Properties
- Each key should be unique
- Key can be any immutable type of object
- `len()` function also works with dictionaries i.e. returns the length of key-value pairs
- A dictionary is a one way tool i.e. We can find the value from key but cannot find they key from value. It works the same way as original dictionary.We can find urdu menaing of word in english but not the english meaning of urdu word.
- The dictionaries are not ordered. We might have different orders when we use `print()` function.
- Dictionaries are not a sequence type. So can we use for loop with dictionaries? No! and Yes! We'll see it in below examples. 

### Creating a Dictionary

 can create a dictionary using curly braces `{}` or the `dict()` function.

#### Example:
```python
# Using curly braces
student_scores : dict[str, int] = {
    "Alice": 85,
    "Bob": 92,
    "Charlie": 78
}

# Using dict() function
student_scores : dict[str,int] = dict(Alice=85, Bob=92, Charlie=78)
```

### Accessing Values

 can access values in a dictionary using the key inside square brackets `[]` or with the `.get()` method.

#### Example:
```python
# Accessing a value using a key
print(student_scores["Alice"])  # Output: 85

# Using the get() method
print(student_scores.get("Bob"))  # Output: 92
```

#### Handling Missing Keys
The `.get()` method is safer for accessing keys, as it returns `None` or a default value if the key is not found, rather than raising a `KeyError`.

#### Example:
```python
# Using square brackets (raises KeyError if key is not found)
# print(student_scores["David"])  # Uncommenting this line would raise KeyError

# Using get() (returns None if key is not found)
print(student_scores.get("David"))  # Output: None

# Providing a default value with get()
print(student_scores.get("David", "Not Found"))  # Output: Not Found
```

## Adding and Updating Items

 can add a new key-value pair or update an existing one using square brackets `[]`.

#### Example:
```python
# Adding a new key-value pair
student_scores["David"] = 88
print(student_scores)  # Output: {'Alice': 85, 'Bob': 92, 'Charlie': 78, 'David': 88}

# Updating an existing key-value pair
student_scores["Alice"] = 90
print(student_scores)  # Output: {'Alice': 90, 'Bob': 92, 'Charlie': 78, 'David': 88}

```

### Removing Items

 can remove items using the `del` statement, the `.pop()` method, or the `.popitem()` method.

#### Example:
```python
# Removing a specific key-value pair using del
del student_scores["Charlie"]
print(student_scores)  # Output: {'Alice': 90, 'Bob': 92, 'David': 88}

# Removing a specific key-value pair using pop()
removed_score = student_scores.pop("David")
print(removed_score)  # Output: 88
print(student_scores)  # Output: {'Alice': 90, 'Bob': 92}

# Removing the last inserted key-value pair using popitem()
last_item = student_scores.popitem()
print(last_item)  # Output: ('Bob', 92)
print(student_scores)  # Output: {'Alice': 90}
```

## Checking if a Key Exists

 can check if a key exists in a dictionary using the `in` keyword.

#### Example:
```python
print("Alice" in student_scores)  # Output: True
print("Charlie" in student_scores)  # Output: False
```

### Iterating Through a Dictionary

We can iterate through the keys, values, or key-value pairs in a dictionary using a `for` loop.

#### Example:
```python
# Iterating through keys
for student in student_scores:
    print(student)
# Output:
# Alice

# Iterating through values
for score in student_scores.values():
    print(score)
# Output:
# 90

# Iterating through key-value pairs
for student, score in student_scores.items():
    print(f"{student}: {score}")
# Output:
# Alice: 90
```

### Dictionary Methods

#### 1. `.keys()` Method
Returns a view object that displays a list of all the keys in the dictionary.

*Example:*
```python
keys = student_scores.keys()
print(keys)  # Output: dict_keys(['Alice'])
```

#### 2. `.values()` Method
Returns a view object that displays a list of all the values in the dictionary.

*Example:*
```python
values = student_scores.values()
print(values)  # Output: dict_values([90])
```

#### 3. `.items()` Method
Returns a view object that displays a list of the dictionary’s key-value tuple pairs.

*Example:*
```python
items = student_scores.items()
print(items)  # Output: dict_items([('Alice', 90)])
```

#### 4. `.update()` Method
Updates the dictionary with elements from another dictionary or from an iterable of key-value pairs.

*Example:*
```python
additional_scores = {"Eve": 95, "Frank": 87}
student_scores.update(additional_scores)
print(student_scores)  # Output: {'Alice': 90, 'Eve': 95, 'Frank': 87}
```

#### 5. `.clear()` Method
Removes all items from the dictionary.

*Example:*
```python
student_scores.clear()
print(student_scores)  # Output: {}
```

#### 5. `.copy()` Method
Removes all items from the dictionary.

*Example:*
```python
sutdent_scroes_copy = student_scores.copy()
print(sutdent_scroes_copy)  # Output: {}
```

### Dictionary Comprehension
We can also apply comprehension method on dictionaries. 

*Example:*
```python
values : dict[int,int] = {x:x for x in range(5)}
print(values)  # Output: {0: 0, 1: 1, 2: 2, 3: 3, 4: 4}
```

*Example:*
```python
fruits : list[str] = ["apple", "banana", "orange"]
fruits_dict : dict[int,str] = {i:fruit for i, fruit in enumerate(fruits)}
print(fruits_dict)  # Output: {0: 'apple', 1: 'banana', 2: 'orange'}
```
