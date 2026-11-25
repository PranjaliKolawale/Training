# Python
### Python Introduction
Python is high level programming language known for its simple and readable syntax.
It has the following feature:
1. Requires fewer lines of code compared to other programming languages like Java.
2. Supports multiple programming paradigms including object-oriented, functional and procedural programming.
3. Dynamically typed and has automatic garbage collection.
4. Widely used in web development, automation, data analysis, artificial intelligence and many other fields.
5. Cross-platform, works on windows, Mac and Linux without major changes.
6. Used by top tech companies like Google, Netflix and NASA.

### Input and Output in Python
The print() function is used for output in various formats and the input() function enables interaction with users.

##### Taking input using python
Python's input function is used to take user input. By default, it returns the user input in form of a string.

```
name = input("Enter your name:")
print("Hello,", name, "!Welcome!")
```

##### Printing Output using print()
print() function allows us to display text, variables and expressions on the console. In the below example, "Hello World!" is a string literal enclosed within double quotes. When executed, this 
statement will output the text to the console.
```
print("Hello, World!")
```

##### Python Variables
Variables are used to store data that can be referenced and manipulated during program execution. A variables is essentially a name that is assigned to a value.
- Unlike Java and many other languages, Python variables do not require explicit declaration of type.
- Type of the variable is inferred based on the value assigned.

##### Rules for Naming Variables
To use variables correctly, the following naming rules should be followed:
1. Names can contain letters, digits and underscores (_).
2. The first character cannot be digit.
3. Names are case-sensitive, so myVar and myvar are treated differently.
4. Keywords such as if, else and for cannot be used as variables names.

### Assigning Values to Variables
1. Basic Assignment: Variables are assigned values using = operator.
2. Dynamic Typing: Python is dynamically typed, so the same variable can store different data types execution.
3. Assigning Same Value: Same value can be assigned to multiple variable in a single line.

### Concept of Object Reference
In Python, an object reference is a variable that refers to an object stored in memory. The variable does not directly contain object, it holds a reference that allows us to access the object.
1. Basic Example
   ```
   a = 10
   b = "Hello"
   c = [10, 20, 30]

   print(a)
   print(b)
   print(c)
   ```

   Here:
   - a refers to an integer object(10).
   - b refers to a string object("Hello")
   - c refers to a list object ([10, 20, 30])
  
  2. Multiple References to the same object.
     ```
     a = [10, 20, 30]
     b = a

     b.append(40)

     print(a)
     print(b)
     ```
     Output:
     [10, 20, 30, 40]
     [10, 20, 30, 40]

     Explanation:
     - a creates a list objects.
     - b = a makes b refer to the same list object.
     - b.append(40) modifies that object.
     - Since both variable refers to the same object, the change is visible through both.

    3. Different references to different objects
    ```
    a = [10, 20, 30]
    b = [10, 20, 30]

    b. append(40)

    print(a)
    print(b)
    ```

    Output:
    [10, 20, 30]
    [10, 20, 30, 40]

    Here, Python creates two separate list objects. Therefore modifying b does not affect a.

    4. Checking Object Identity
    ```
    a = [10, 20, 30]
    b = a
    c = [10, 20, 30]

    print(a is b)
    print(a is c)
    ```
    Remember:
    - = assigns an object reference.
    - is checks whether two references point to the same object.
    - == checks whether two objects have equal values.

    Key Takeaway: In Python, variables are references to objects, and multiple variables can refer to the same object.

### Operators
Operators are used to perform operations on values and variables.
1. Operands: Special Symbols like -, +, *, /, etc.
2. Operands: Value on which the operator is applied.

##### Types of operator in Python
| Type | Operators |
| Arithmetic Operators | +, -, *, /, % |
| Relational Operators | <, <=, >, >=, ==, != |
| Logical Operators | AND, OR, NOT |
| Bitwise Operators | &, |, ^, ~, <<, >> |
| Assignment Operators | =, +=, -=, *=, %= |
| Ternary Operators | x if condition else y |
| Identity Operators | is, is not |

##### Arithmetic Operators
Arithmetic operators are used to perform basic mathematical operations like addition, substraction, multiplication and division.
In Python, the division operator (/) returns a floating-point result, while floor division (//) returns an integer result.
Code:
```
a = 15
b = 4

print("Addition:", a+b)
print("Substraction:", a-b)
print("Multiplication:", a*b)
print("Division:", a/b)
print("Floor Division:", a//b)
print("Modulus:", a%b)
print("Exponentiation:", a**b)
```
Output:
```
Addition: 19
Substraction: 11
Multiplication: 60
Division: 3.75
Floor Division: 3
Modulus: 3
Exponentiation: 50625
```

##### Comparison Operators
Comparison operators compares values. It either returns True or False according to the condition.
Code:
```
a = 13
b = 33

print(a>b)
print(a<b)
print(a==b)
print(a!=b)
print(a>=b)
print(a<=b)
```
Output:
```
False
True
False
True
False
True
```

##### Logical Operators
Logical operators performs Logical AND, Logical OR, and Logical NOT operations. It is used to combine conditional statements.
The precedence of Logical Operators in Python is as follows:
1. Logical not
2. Logical and
3. Logical or

Code:
```
a = True
b = False
print(a and b)
print(a or b)
print(not a)
```
Output:
```
False
True
False
```

##### Bitwise Operators
Bitwise operators act on bits and perform bit-by-bit operations. These are used to operate on binary numbers.
Bitwise Operators in Python as follows:
1. Bitwise NOT
2. Bitwise Shift
3. Bitwise AND
4. Bitwise XOR
5. Bitwise OR

Code:
```
a = 10
b = 4

print(a & b)
print(a | b)
print(~a)
print(a ^ b)
print(a >> 2)
print(a << 2)
```
Output:
```
0
14
-11
14
2
40
```
##### Assignment Operators
Assignment operators are used to assign values to the variables. This operator is used to assign the value of the right side of the expression to the left side of the operand.
Code:
```
a = 10
b = a
print(b)
b += a
print(b)
b -= a
print(b)
b *= a
print(b)
b <<= a
print(b)
```
Output:
```
10
20
10
100
102400
```
##### Identity Operators
"is" and "is not" are the identity operators and both are used to check if two values are located on the same part of the memory. Two variables that are equal do not imply that they are identical.
is -> True if the operands are identical
is not -> True if the operands are not identical

Code:
```
a = 10
b = 20
c = a

print(a is not b)
print(a is c)
```
Output:
```
True
True
```

##### Membership Operators
"in" and "not in" are the membership operators that are used to test whether a value or variable is in sequence.
"in" -> True if value not found in the sequence
"not in" -> True if value is not found in sequence

Code:
```
x = 24
y = 20
my_list = [10, 20, 30, 40, 50]

if (x not in my_list):
    print("x is NOT present in given list")
else:
    print("x is present in given list")

if (y in my_list):
    print("y is present in given list")
else:
    print("y is NOT present in given list")
```
Output:
```
x is NOT present in given list
y is present in given list
```

### Ternary Operator
Ternary operators also known as conditional expressions are operators that evaluate something based on a condition being true or false. It was added to Python in version 2.5. 
It simply allows testing a condition in a single line replacing the multiline if-else, making the code compact.

Syntax :  [on_true] if [expression] else [on_false] 

Code:
```
a, b = 10, 20
min = a if a < b else b

print(min)
```
Output:
```
10
```

### Precedence and Associativity Operator
Operator precedence and associativity determine the priorities of the operator.
##### Operator Precedence
This is used in an expression with more than one operator with different precedence to determine which operation to perform first.
```
expr = 10 + 20 * 30
print(expr)
name = "Alex"
age = 0

if name == "Alex" or name == "John" and age >= 2:
    print("Hello! Welcome.")
else:
    print("Good Bye!!")
```
Output:
```
610
Hello! Welcome.
```
##### Operator Associativity
If an expression contains two or more operators with the same precedence then Operator Associativity is used to determine. It can either be Left to Right or from Right to Left.
Code:
```
print(100 / 10 * 10)
print(5 - 2 + 3)
print(5 - (2 + 3))
print(2 ** 3 ** 2)
```
Output:
```
100.0
6
0
512
```
### Keywords
| Category | Keywords |
|----------|----------|
| Value Keywords | True, False, None |
| Conditional Keywords | if, elseif, else |
| Looping Keywords | for, while, break, continue, pass |
| Logical and Looping Keywords | and, or, not, in, is |
| Function Keywords | def, return, lambda, yield |
| Class and Object Keywords | class, del |
| Exception Handelling Keyword | try, except, finally, raise, assert |
| Module and Import Keywords | import, from, as |
| Scope Management Keywords | global, nonlocal |
| Asynchronous Programming Keywords | async, await |
| Context Management Keywords | with |

##### Difference Between Keywords, Variables and Identifiers in Python
| Basis | Keywords | Variables | Identifiers |
|-------|----------|-----------|-------------|
| Definition | Reserved words that have predefined meanings in Python | Names used to store or refer to data in a program. | Names used to identify variables, functions, classes, etc. |
| Purpose | Define the syntax and structure of python programs. | Hold references to value or objects. | Provide unique names to programming elements within their scope. |
| Creation | Predefined by Python. | Created by assigning values. | Defined by the programmer. |
| Modification | Cannot be redefined as ordinary identifiers. | Can refer to differnt values during program execution. | Names are assigned when programming elements are defined. |
| Naming Rules | Must be used according to Python's Syntax. | Must follow Python's Identifier naming rules. | Must follow Python's naming rules and cannot be keywords. |
| Examples | if, else, for, while, class, def | age, name, salary, marks | age, calculate_sum, Student, student_name |




     
     


