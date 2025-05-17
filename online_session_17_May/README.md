# Falsy values in Python

These values are evaluated to 'false' that's why we call it `falsy` values.

```python
value_01 : None = None
value_02 : int = 0
value_03 : float = 0.0
value_04 : str = ""
Value_05 : bool = False
value_06 : list[None] = []
```
And all other empty collections and sequences are also `falsy`.


---


# Conditional Statements in Python

## The Problem: Making Decisions in Code

Imagine we're building a simple app that recommends activities based on the weather. On a sunny day, we want to suggest going for a walk, while on a rainy day, we'd suggest staying indoors and reading a book. But what if it's cloudy or snowing? How do we make our app smart enough to handle these different scenarios?

Without a way to make decisions, our app would always suggest the same thing, no matter the weather. This is where we hit our first roadblock as budding programmers: **How do we make our code choose the right path?**

## The Solution: conditional statements in Python

Python, like any language, needs a way to handle different situations. This is where **conditional statements** come into play. These are the structures that allow our code to decide what to do next based on certain conditions. In Python, we use `if`, `elif`, and `else` to guide these decisions.

### The Story of Choices: `if`, `elif`, and `else`

Let’s dive into the story of how Python makes decisions.

1. **The `if` Statement**:

   - Think of `if` as the gatekeeper. It checks a condition and decides if the code block that follows should run.
   - For example: If the weather is sunny, the gatekeeper will open the door to the "go for a walk" suggestion.

   ```python
   weather : str = "sunny"

   if weather == "sunny":
       print("It's a beautiful day! Go for a walk.")
   ```

   We can also use `else` statement in above exmple.

   - For example: We want to specify something else is done if our condition is not met, then we use `else` statement.

   ```python
   weather : str = "sunny"

   if weather == "sunny":
       print("It's a beautiful day! Go for a walk.")
   else:
       print("Read the book")
   ```

   **Ternary Operator (Optional):**

   - Python offers another way to write the `if` `else` code with less number of lines i.e. **Ternary Operator**. Let's see how can we use Ternary Operator to write the same code.

   ```python
   # We can also write the above example like so.
   weather : str =  "sunny"

   if weather == "sunny":
       message : str = "It's a beautiful day! Go for a walk."
   else:
       message : str = "Read the Book"
   print(message)
   ```

   Nothing is changed so far, we just refactored the code. Also note, we've used ternary operator yet but we made a ground for understanding ternary operator.

   **_Use of Ternary Operator_**

   ```python
   weather : str == "sunny"
   message : str = "It's a beautiful day! Go for a walk." if weather == "sunny" else "Read the book"
   print(message)
   ```

   - By using ternary operator, we write the `if` `else` block in a single line.
   - Ealier, we wrote 5 lines of code for first example and 6 lines of code for second example.
   - With ternary operator, we just wrote 3 lines of code which provided the same result.

2. **The `elif` Statement**:

   - What if we've multiple choices, how do we make the decision then?
   - What if the weather isn’t sunny? That’s where `elif` (short for "else if") comes in. It's the gatekeeper’s assistant, ready to check another condition if the first one fails.
   - For example: If the weather is not sunny but cloudy, the assistant will suggest taking an umbrella just in case.

   ```python
   weather : str = "cloudy"

   if weather == "sunny":
       print("It's a beautiful day! Go for a walk.")
   elif weather == "cloudy":
       print("It might rain. Better take an umbrella.")
   ```

3. **The `else` Statement**:

   - Finally, there’s `else`, the last resort. If all other conditions fail, `else` steps in to provide a default action.
   - For example: If the weather isn’t sunny or cloudy, and perhaps it’s raining or snowing, `else` will suggest a cozy indoor activity.

   ```python
   weather : str = "rainy"

   if weather == "sunny":
       print("It's a beautiful day! Go for a walk.")
   elif weather == "cloudy":
       print("It might rain. Better take an umbrella.")
   else:
       print("Stay indoors and read a book.")
   ```

## Nested Conditional Statements

Will be done in onsite class

## Why It Matters

By using `if`, `elif`, and `else`, we give our program the power to make decisions just like we do in real life. This makes our code dynamic, flexible, and smart enough to handle different situations.

With conditional statements, we can solve problems like:

- **Customizing user experiences**: Show different messages or suggestions based on user input or external factors.
- **Automating tasks**: Only perform certain actions when specific conditions are met.
- **Creating complex algorithms**: Make our programs more sophisticated by handling multiple scenarios with ease.

## Examples

Here are some real-world examples that demonstrate the use of `if`, `elif`, nested `if`, and multiple `if` conditions in Python.

### 1. Simple `if` Statement

**Scenario**: A user wants to check if they have enough balance to make a purchase.

```python
balance : int = 150
price : int = 100

if balance >= price:
    print("Purchase successful!")
```

**Explanation**: The `if` statement checks if the user's balance is greater than or equal to the price. If true, the purchase is successful.

### 2. `if`-`elif`-`else` Chain

**Scenario**: A system that grades students based on their score.

```python
score : int = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

**Explanation**: The program checks the score against several conditions using `if` and `elif`. If none of the conditions match, the `else` block runs, assigning an "F" grade.

### 3. Nested `if` Statement

**Scenario**: A store offers a discount only to members who have also made purchases above a certain amount.

```python
is_member : bool = True
purchase_amount : int = 250

if is_member:
    if purchase_amount > 200:
        print("You are eligible for a 10% discount!")
    else:
        print("Spend more than $200 to get a discount.")
else:
    print("Become a member to enjoy discounts.")
```

**Explanation**: The first `if` checks if the user is a member. If true, it checks if their purchase amount exceeds $200 using a nested `if`. Based on these conditions, the program decides if the user is eligible for a discount.

### 4. Multiple `if` Statements (Independent Conditions)

**Scenario**: A smart home system that checks several independent conditions to set up the house for the night.

```python
lights_on : bool = True
doors_locked : bool = False
windows_closed : bool = True

if lights_on:
    print("Turning off the lights.")
if not doors_locked:
    print("Locking the doors.")
if windows_closed:
    print("All windows are closed.")
```

**Explanation**: Each `if` statement is independent and checks a different condition. The system performs actions like turning off lights, locking doors, and checking windows, regardless of the other conditions.


### 5. Nested `if` with `elif` and `else`

**Scenario**: A restaurant ordering system that checks if a user has chosen a meal and then checks for special requests.

```python
meal_selected : str = "burger"
add_cheese : bool = True

if meal_selected == "burger":
    print("Burger selected.")

    if add_cheese:
        print("Adding cheese.")
    else:
        print("No cheese added.")

elif meal_selected == "pizza":
    print("Pizza selected.")
else:
    print("Please select a meal.")
```

**Explanation**: The system first checks if a meal is selected, then performs additional checks (like adding cheese) using nested `if` statements. If the meal isn’t a burger, it checks for other meals with `elif`.

These examples illustrate how `if`, `elif`, nested `if`, and multiple independent `if` statements can be used to handle various real-world scenarios in Python.

---

# For Loop

The for loop is used to iterate over a sequence (like a list, tuple, set, or string) or any other iterable object. It allows you to execute a block of code a specific number of times, usually determined by the length of the sequence or the range of values.

### Syntax

```
for item in iterable:
    # Execute this block of code
```

### Iterating over a list

```
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### Iterating over a string

```
for letter in "Python":
    print(letter)
```

### Using range() in a for loop

```
for i in range(5):
    print(i)
```

### Specifying a start and end in range()

```
for i in range(2, 6):
    print(i)
```

### Using a step in range()

```
for i in range(1, 10, 2):
    print(i)
```

### for Loop with zip()
Iterating over two lists simultaneously

```
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]

for name, age in zip(names, ages):
    print(f"{name} is {age} years old")
```

---

# Nested for Loops

Nested for loops are used when you need to perform an action that involves iterating over multiple sequences or when dealing with multi-dimensional data (like a matrix or list of lists).


### Iterating over a list of lists

```
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in matrix:
    for element in row:
        print(element, end=" ")
    print()
```

---
# The While Loop:

```json
while you have peanuts
    keep eating
```
- `while` and `if` both checks the conditions. If the condition is met (`True`), the instructions in `if` block exeuctures only once. However, in `while`, if the condition is met (`True`), the instructions in the `while` block runs more than once. 

- If condition evaluates to `False` the instuctions in the block never runs. 

- There should be a mechanism in the body to change the condition value. Otherwise the body will keep executing forever. 

## Situation
You have a class that runs until 6 PM. During this time, you want to keep learn Python. You don’t want to stop coding until the clock hits 6 PM.


In a real-life scenario, you might keep checking the time every few minutes while you’re coding to see if it’s 6 PM yet:

	1.	Start coding.
	2.	Check the time.
	3.	If it’s not 6 PM, continue coding.
	4.	Repeat this process until it’s 6 PM.

This approach works, but it requires constant attention to the clock, which can be distracting.

# While Loop
The while loop in Python is a control flow statement that allows code to be executed repeatedly based on a given condition. The loop continues to execute as long as the condition evaluates to True. Once the condition becomes False, the loop stops running.

#### syntax
```
while condition:
    # Code block to be executed repeatedly
```

In a programming context, you can automate this process using a while loop that will allow you to keep coding until the time reaches 6 PM.

```
while current_time < 18:  # 18 represents 6 PM in 24-hour format
    print("Still coding... The time is not yet 6 PM.")

print("It's 6 PM! Time to stop coding and end the class.")
```

---

### Example 1: Basic while Loop

```
count = 0
while count < 5:
    print("Count is:", count)
    count += 1
```
Explanation:

	•	The loop starts with count equal to 0.
	•	It prints the value of count and then increments count by 1.
	•	This process repeats until count is no longer less than 5.


### Example 2: while Loop with a Condition
You can use a while loop to keep prompting the user until they enter a valid input.

```
password = ""
while password != "Pass123":
    password = input("Enter the password: ")

print("Access granted")
```


### Example 3: Infinite while Loop
A while loop can run indefinitely if the condition never becomes False. This is known as an infinite loop, and it will continue to run until you manually stop it or break out of it with a break statement.

```
while True:
    print("This loop will run forever")
    # You can include a break condition to exit the loop
```

***Note: Be careful with infinite loops, as they can cause your program to hang if not properly managed.***



