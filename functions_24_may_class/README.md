# Functions in Python
We've used functions many times, like `print()` and `input()`, to make tasks simpler. We've also worked with methods, which are special kinds of functions. Now, it's time to write our own functions, starting with simple ones and progressing to more complex examples.

## Why we need functions
Often, we'll find the same code repeating in our program with minor changes. Copying and pasting might seem convenient, but if an error occurs, fixing it everywhere can be tedious and risky. This is where functions come in. When a piece of code is repeated in multiple places, consider turning it into a function to streamline our code.

As programs grow, they can become difficult to manage. While comments help, too many make the code harder to follow. A well-written function should be concise and easily understood at a glance. Skilled developers break problems into small, isolated tasks, each handled by its own function, keeping the code clean and organized.

## Types of Functions
1. Built-in Functions:
    - We have already used python builtin functions e.g. `print()`, `input()`, `int()`, `float()`.
2. User defined Functions
    - User-defined functions are those functions which are defined by the user, for the user. 

## When to create a function
1. When a particular fragment of the code begins to appear in more than one place, consider the possibility of isolating it in the form of a function invoked.
2. When a piece of code becomes so large that reading and understating it may cause a problem, consider dividing it into separate, smaller
problems, and implement each of them in the form of a separate function.
3. Decompose the problem to allow the product to be implemented as a set of separately written functions packed together in different modules.

**Example**
```python
a : int = int(input("Enter a value"))
print(a)

b : int = int(input("Enter a value"))
print(b)

c : int = int(input("Enter a value"))
print(c)

```
We have written above example to get a number from user and print that number. We are doing this 3 times. 
This code is absolutely fine and will work. But what if our client/teacher asks as to print the number in this form. "User gave the number <number>".
So we have to change the print statement on multiple lines. 

In above example, we are repeating our code. We can use function here like so. 
```python
def print_number():
    a : int = int(input("Enter a value"))
    print(a)
```
Now see, we have to change the print on just a single line. Let's chage it as per client/teacher requirement.
```python
def print_number():
    a : int = int(input("Enter a value"))
    print(f"User gave the number {a}")
```

## How to create and use the function
For functions, we have to first define a function, then invoke (use) the function wherever it is required. 

**Step-1: Define (Create) a function**
Here is the syntax to create a function.
- We start from keyword `def`.
- Then we add function name. `def function_name`. The naming conventions for naming the functions is same as naming the variable in python.
- Then we add paranthesis `def function_name()`.
- And finally, we add colon `def function_name():`
- After the colon, comes our function body. Function body contains the code/logic of the task function in bening written for. 

Now our funciton has been defined. We can use it wherever we require.

**Step-2: Invoke (Use) a function**
We can use our function like so 
```python
function_name()
```
----

# Function Parameters
In this section, we'll learn about parameterless and parameterized functions. 

## What are function parameters?
So far we learnt that functions perform a specific task. To perform the task, in some cases, function needs some inputs/data and in other cases, it doesn't.
- Parameters simply can be said the inputs/data required by the function to perform a specific task. 
- The inputs/data is provided from outside the function but we have to mention them while defining the functions. 
- Parameters only exist inside the function.
- parameters are provided in paranthesis of the function. 

Let's have a look at parameterless and parameterized function.

## Parameterless Fucntions:
These type of functions don't require parameters.

```python
def greetings():
    print("Hello Rehan!")

greetings() #Output: Hello Rehan!
```

## Parameterized Fucntions:
These type of functions require parameters.

```python
my_name : str = "Rehan"
def greetings(name):
    print(f"Hello {name}!")

greetings(my_name) #Output: Hello Rehan!
```
- `name` here, is the parameter provided to the function. 
- Now our function has become more dynamic. We can provide any name, it will greet that person.
- `my_name` is the argument provided at the time of function invokation.

## What are Arguments?
Arguments are the actual values you pass to a function when you call it. These values get assigned to the function’s parameters.

```python
greetings("Rehan") 
```
`Rehan` is the argument provided to the function. 
- Arguments live outside the function.
- Arguments can be accessed inside the function. 
**Parameters**
- Parameters are defined in function at the time of function definition.
- Parameters only live inside function. They don't have outside scope.

We'll discuss it in details in `Scope` section.

---
# Function Return
## 1. Reutrn with expression
So far we only discussed the functions which perform specific task but do not provide results. Now we'll discuss the functions which do provide a result and we get this result through `return` keyword. 

Let's look at example of a function which takes 2 parameters (numbers), add them (perform a task) and return the result. 

```python
# Define a function
def addition(first_number:int, second_number:int)->int:
    result : int = first_number + second_number
    return result


print(addition(5, 8)) # Output: 13
# Can also do like this
get_sum : int = addition(5,8)
print(get_sum) #Output: 13

```
If we take example of python builin functions, `print()` function doesn't return anything while `int()` returns and integer value. 

Here we are using return with expression. `return result` here 'result' is the expression.

## 2. Reutrn without expression
Sometimes, we use `return` keyword without expression. What will function return in that case. Well, function will then return `None` 

**Usecase**
In above example, we were just getting the sum of 2 numbers. Let's add a scenarion. We want our function to add the value only when both of the numbers are non zero. Let's implement it inside the function.

```python
# Define a function
def addition_non_zero(first_number:int, second_number:int)->int | None:
    if first_number > 0 and second_number > 0:
        result : int = first_number + second_number
        return result


get_sum : int | None = addition_non_zero(5,8)
print(get_sum) # Output: 13

get_sum : int | None = addition_non_zero(0,8)
print(get_sum) # Output: None

```

## 3. Return Multiple values
Remember, function will always return a single value. So how can we return if we need multiple values. We use tuple in that case. Function still returns a single value (a tuple), but we already know that we can unpack the tuple. 

**Example**
```python
def mul_and_add(a:int, b:int)-> tuple[int, int]:
    multiplication : int = a * b
    addition : int = a + b
    return multiplication, addition

result = mul_and_add(5, 4)
print(result)  # Output: (20, 9)

# We can unpack it like so
mul_result, add_result = mul_and_add(5, 4)
print(f"Multiplication result:{mul_result}")
print(f"Addition result:{add_result}")
```

## 4. Return a list

```python
def generate_even_numbers(limit):
    even_numbers = [i for i in range(limit) if i % 2 == 0]
    return even_numbers

result = generate_even_numbers(10)
print(result)  # Output: [0, 2, 4, 6, 8]
```

## 5. Return a dictionary
```python
def get_student_info(name, age, course):
    return {
        "name": name,
        "age": age,
        "course": course
    }

student_info = get_student_info("John", 21, "Mathematics")
print(student_info)  # Output: {'name': 'John', 'age': 21, 'course': 'Mathematics'}
```

----
# Positional Arguments in Python Functions
When defining a function, we can specify parameters that act as placeholders for values the function will receive. These values, called **arguments**, are passed when we call the function.

One common way to pass arguments is using **positional arguments**. This means the arguments are assigned to parameters based on their position in the function call.


## What Are Positional Arguments?

Positional arguments are arguments that are passed to a function based on the order they appear in the function call. The first argument is assigned to the first parameter, the second to the second parameter, and so on.

### Syntax:
```python
def function_name(parameter1, parameter2, ...):
    print(f"Parameter 1: {parameter1}")
    print(f"Parameter 2: {parameter2}")
    return parameter1-parameter2
```

When calling the function, we pass values for each parameter in the same order as they were defined.

```python
function_name(argument1, argument2, ...)
```

---

## How Positional Arguments Work

The following example illustrates a function that uses positional arguments:

```python
def greet(name, message):
    print(f"Hello {name}, {message}")

greet("Ali", "Welcome to Python!")  # Output: Hello Ali, Welcome to Python!
```

In the example:
- `"Ali"` is passed as the first argument and is assigned to the `name` parameter.
- `"Welcome to Python!"` is passed as the second argument and is assigned to the `message` parameter.

The position of the arguments is crucial here. If we change the order, the meaning of the arguments changes.

```python
greet("Welcome to Python!", "Ali")  # Output: Hello Welcome to Python!, Alice
```

---

## Examples of Positional Arguments

Here are some more examples to demonstrate how positional arguments work:

### Example 1: A Function with Two Parameters

```python
def add_numbers(a, b):
    return a - b

result = add_numbers(10, 5)
print(result)  # Output: 5
```

In this example, `10` is passed to the parameter `a` and `5` is passed to `b`. The difference of the two is returned.
However, we the result will be changed if we pass the parameter in opposite order. Do check that out. So the order is crucial in positional arguments.

### Example 2: Function with Three Positional Arguments

```python
def describe_person(name, age, city):
    print(f"{name} is {age} years old and lives in {city}.")

describe_person("Musa", 25, "New York")
# Output: Musa is 25 years old and lives in New York.
```

Here, the arguments are passed in the order corresponding to the parameters: `name`, `age`, and `city`.

---

## Multiple Positional Arguments

We can pass any number of positional arguments to a function as long as they match the number of parameters defined in the function defination.

### Example 3: Function with Multiple Parameters

```python
def multiply(x, y, z):
    return x * y * z

result = multiply(2, 3, 4)
print(result)  # Output: 24
```

The function `multiply` accepts three positional arguments, and the result is the product of the three numbers.

---

## Best Practices for Positional Arguments

- **Order Matters**: Since the arguments are mapped to parameters based on their position, always ensure they are passed in the correct order.
  
- **Matching Parameters**: Ensure that the number of arguments matches the number of parameters in the function definition. If the numbers don’t match, Python will raise an error.

```python
def subtract(a, b):
    return a - b

# Correct usage
print(subtract(10, 5))  # Output: 5

# Incorrect usage
# print(subtract(10))  # Error: subtract() missing 1 required positional argument: 'b'
```

- **Readability**: It’s essential to pass arguments in a way that makes the function call readable and understandable.

---

## Conclusion

Positional arguments in Python allow us to pass values to a function in a straightforward manner, based on their position. Understanding how to use positional arguments effectively is crucial when writing clean, functional Python code. Just remember that order matters, and the number of arguments must match the function’s parameter list.

For more advanced functionality, Python also supports keyword arguments, default arguments, and variable-length arguments (`*args` and `**kwargs`), but positional arguments are the foundation of function calls in Python. We will see `*args` and `**kwargs` in coming sections.

---

# `*args` and `**kwargs` in Python Functions

Python functions allow for a wide range of flexibility when it comes to passing arguments. Two powerful features of Python are `*args` and `**kwargs`, which let us pass a variable number of arguments to a function. These features give developers more control and flexibility over how functions handle data.


## What are `*args` and `**kwargs`?

- **`*args`**: Allows a function to accept any number of positional arguments as a tuple.
- **`**kwargs`**: Allows a function to accept any number of keyword arguments as a dictionary.

These features provide flexibility when we don’t know in advance how many arguments will be passed to our function.

---

## How `*args` Work

When a function has `*args` as a parameter, it can accept any number of positional arguments. Inside the function, these arguments are available as a tuple.

### Syntax:
```python
def function_name(*args):
    # args is a tuple containing all positional arguments
    for arg in args:
        print(arg)
```

### Example:
```python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3))  # Output: 6
print(sum_numbers(4, 5, 6, 7))  # Output: 22
```

In this example, the function `sum_numbers` accepts any number of positional arguments and returns their sum.

---

## How `**kwargs` Work

When a function has `**kwargs` as a parameter, it can accept any number of keyword arguments. Inside the function, these arguments are available as a dictionary where the keys are the argument names and the values are the corresponding values.

### Syntax:
```python
def function_name(**kwargs):
    # kwargs is a dictionary containing all keyword arguments
    for key, value in kwargs.items():
        print(f"{key}: {value}")
```

### Example:
```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Ali", age=25, city="New York")
# Output:
# name: Ali
# age: 25
# city: New York
```

In this example, `print_info` accepts any number of keyword arguments and prints them.

---

## Examples of Using `*args`

### Example 1: A Function with Multiple Positional Arguments

```python
def multiply_numbers(*args):
    result = 1
    for num in args:
        result *= num
    return result

print(multiply_numbers(2, 3, 4))  # Output: 24
print(multiply_numbers(1, 5, 10))  # Output: 50
```

In this function, `multiply_numbers` can accept a variable number of arguments and multiply them together.

### Example 2: Passing a List as `*args`

We can also pass a list of arguments using the `*` operator.

```python
numbers = [1, 2, 3, 4]
print(multiply_numbers(*numbers))  # Output: 24
```

Here, the list `numbers` is unpacked into positional arguments using `*`.

---

## Examples of Using `**kwargs`

### Example 1: Function with Multiple Keyword Arguments

```python
def greet(**kwargs):
    if 'name' in kwargs:
        print(f"Hello {kwargs['name']}!")
    else:
        print("Hello Guest!")

greet(name="Bob")  # Output: Hello Bob!
greet()  # Output: Hello Guest!
```

In this example, `greet` can accept any number of keyword arguments and checks if a `name` argument is provided.

### Example 2: Passing a Dictionary as `**kwargs`

We can pass a dictionary of keyword arguments using the `**` operator.

```python
person_info = {"name": "Ali", "age": 30}
greet(**person_info)  # Output: Hello Ali!
```

The dictionary `person_info` is unpacked and passed as keyword arguments to the `greet` function.

---

## Combining `*args` and `**kwargs`

We can use both `*args` and `**kwargs` in the same function to handle a combination of positional and keyword arguments.

### Example 1: Handling Both Positional and Keyword Arguments

```python
def display_info(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

display_info(1, 2, 3, name="Ali", age=25)
# Output:
# Positional arguments: (1, 2, 3)
# Keyword arguments: {'name': 'Ali', 'age': 25}
```

In this example, `display_info` accepts both positional and keyword arguments and prints them separately.

### Example 2: Function with Default Arguments, `*args`, and `**kwargs`

```python
def order_pizza(size="medium", *toppings, **details):
    print(f"Size: {size}")
    print(f"Toppings: {', '.join(toppings)}")
    print("Details:")
    for key, value in details.items():
        print(f"  {key}: {value}")

order_pizza("large", "pepperoni", "mushrooms", name="Ali", delivery_time="18:00")
# Output:
# Size: large
# Toppings: pepperoni, mushrooms
# Details:
#   name: Ali
#   delivery_time: 18:00
```

In this example, `order_pizza` accepts a default argument, multiple toppings as `*args`, and order details as `**kwargs`.

---

## Best Practices for `*args` and `**kwargs`

1. **Use `*args` for unknown number of positional arguments**: Use `*args` when you don’t know how many positional arguments will be passed to your function.
2. **Use `**kwargs` for optional keyword arguments**: Use `**kwargs` when you want to allow optional keyword arguments.
3. **Order matters**: When defining a function with both `*args` and `**kwargs`, the order should be: positional arguments, `*args`, default parameters, and then `**kwargs`.
4. **Descriptive variable names**: While `*args` and `**kwargs` are the convention, you can give them more descriptive names like `*numbers` or `**options` to improve readability.



----

# Lambda Functions in Python

In Python, **lambda functions** are anonymous, inline functions that can have any number of arguments but only a single expression. They are often used for simple operations and as a shorthand in situations where defining a full function would be unnecessary or cumbersome.

## What is a Lambda Function?

A **lambda function** in Python is a small anonymous function defined with the `lambda` keyword. Unlike regular functions defined using `def`, a lambda function is a single expression. Lambda functions are often used as arguments to higher-order functions like `map()`, `filter()`, and `sorted()`.

### Key Points:

- **Anonymous**: Lambda functions are not bound to a name, hence they're referred to as anonymous functions.
- **Single expression**: They contain only one expression and automatically return the result of that expression.
- **Inline**: They are often used inline and passed as arguments to functions.

---

## Syntax of a Lambda Function

The syntax of a lambda function is straightforward:

```python
lambda arguments: expression
```

- **`lambda`**: The keyword used to define a lambda function.
- **`arguments`**: A comma-separated list of parameters (just like a normal function).
- **`expression`**: A single expression that is evaluated and returned.

### Example of Lambda Syntax:

```python
# A lambda function that adds 10 to a number
add_ten = lambda x: x + 10

# Call the lambda function
print(add_ten(5))  # Output: 15
```

---

## Examples of Lambda Functions

### Example 1: Basic Lambda Function

A simple lambda function that takes one argument and returns its square.

```python
# Lambda function to square a number
square = lambda x: x * x

print(square(4))  # Output: 16
```

### Example 2: Lambda with Multiple Arguments

Lambda functions can take multiple arguments just like regular functions.

```python
# Lambda function to multiply two numbers
multiply = lambda a, b: a * b

print(multiply(3, 5))  # Output: 15
```

### Example 3: Using Lambda with Built-in Functions

Lambda functions are commonly used with Python’s built-in higher-order functions like `map()`, `filter()`, and `sorted()`.

#### `map()` with Lambda:

`map()` applies a lambda function to each item in a list or iterable.

```python
numbers = [1, 2, 3, 4, 5]

# Square each number using map and lambda
squared_numbers = list(map(lambda x: x ** 2, numbers))

print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

#### `filter()` with Lambda:

`filter()` returns elements of a list that satisfy a given condition (lambda function).

```python
numbers = [1, 2, 3, 4, 5, 6]

# Filter out even numbers
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))

print(even_numbers)  # Output: [2, 4, 6]
```

#### `sorted()` with Lambda:

`sorted()` can use a lambda function as a `key` to sort based on custom criteria.

```python
students = [("Ali", 85), ("Zara", 90), ("Bob", 75)]

# Sort by student scores (second item in tuple)
sorted_students = sorted(students, key=lambda x: x[1])

print(sorted_students)  # Output: [('Bob', 75), ('Ali', 85), ('Zara', 90)]
```

---

## Use Cases for Lambda Functions

1. **Simple Operations**: Lambda functions are ideal for small, simple operations where defining a full `def` function would be unnecessary.

   Example: Applying a simple mathematical operation inline:

   ```python
   add_five = lambda x: x + 5
   print(add_five(10))  # Output: 15
   ```

2. **Higher-Order Functions**: When working with functions like `map()`, `filter()`, and `reduce()`, lambda functions provide a concise and readable way to pass behavior to the function.
3. **Sorting**: Lambda functions are often used with the `sorted()` function to customize sorting based on specific fields.

4. **Functional Programming**: Lambdas are useful in functional programming patterns where functions are passed as arguments or returned from other functions.

---

## Limitations of Lambda Functions

1. **Single Expression**: Lambda functions are limited to one expression, which can sometimes make them less readable if complex logic is required.
2. **No Statements**: Unlike normal functions, lambda functions can't contain statements such as loops, print, or multi-line logic.

3. **Less Readable for Complex Operations**: While lambda functions are concise, they can reduce readability if overused or used for complex logic.

4. **No Annotations**: Lambda functions don't support function annotations (type hints).
---
