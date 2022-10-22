---
title: Conditions-Control-Structures
author: sumendar
date: '2017-09-30'
slug: Conditions-Control-Structures
categories: ['python', 'conditional statements']
tags: ['basics']
subtitle: 'subtitle'
---

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#if--Statements" data-toc-modified-id="if--Statements-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>if  Statements</a></span></li><li><span><a href="#if...else-Statement" data-toc-modified-id="if...else-Statement-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>if...else Statement</a></span></li><li><span><a href="#if...elif...else-Statement" data-toc-modified-id="if...elif...else-Statement-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>if...elif...else Statement</a></span></li><li><span><a href="#Nested-if-statements" data-toc-modified-id="Nested-if-statements-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>Nested if statements</a></span></li><li><span><a href="#Practice" data-toc-modified-id="Practice-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>Practice</a></span></li><li><span><a href="#Iterables-and-Iterators" data-toc-modified-id="Iterables-and-Iterators-6"><span class="toc-item-num">6&nbsp;&nbsp;</span>Iterables and Iterators</a></span></li><li><span><a href="#while-Loops" data-toc-modified-id="while-Loops-7"><span class="toc-item-num">7&nbsp;&nbsp;</span>while Loops</a></span></li><li><span><a href="#for-Loops" data-toc-modified-id="for-Loops-8"><span class="toc-item-num">8&nbsp;&nbsp;</span>for Loops</a></span></li><li><span><a href="#range()" data-toc-modified-id="range()-9"><span class="toc-item-num">9&nbsp;&nbsp;</span>range()</a></span></li><li><span><a href="#enumerate¶" data-toc-modified-id="enumerate¶-10"><span class="toc-item-num">10&nbsp;&nbsp;</span>enumerate¶</a></span></li><li><span><a href="#The-break-statement" data-toc-modified-id="The-break-statement-11"><span class="toc-item-num">11&nbsp;&nbsp;</span>The break statement</a></span></li><li><span><a href="#The-continue-statement" data-toc-modified-id="The-continue-statement-12"><span class="toc-item-num">12&nbsp;&nbsp;</span>The continue statement</a></span></li><li><span><a href="#Python-pass-statement" data-toc-modified-id="Python-pass-statement-13"><span class="toc-item-num">13&nbsp;&nbsp;</span>Python pass statement</a></span></li><li><span><a href="#Comprehensions" data-toc-modified-id="Comprehensions-14"><span class="toc-item-num">14&nbsp;&nbsp;</span>Comprehensions</a></span><ul class="toc-item"><li><span><a href="#comprehension-for-lists" data-toc-modified-id="comprehension-for-lists-14.1"><span class="toc-item-num">14.1&nbsp;&nbsp;</span>comprehension for lists</a></span></li><li><span><a href="#comprehension-for-dictionaries" data-toc-modified-id="comprehension-for-dictionaries-14.2"><span class="toc-item-num">14.2&nbsp;&nbsp;</span>comprehension for dictionaries</a></span></li><li><span><a href="#comprehension-for-sets" data-toc-modified-id="comprehension-for-sets-14.3"><span class="toc-item-num">14.3&nbsp;&nbsp;</span>comprehension for sets</a></span></li></ul></li><li><span><a href="#Errors-Handling:-try-except-and-finally" data-toc-modified-id="Errors-Handling:-try-except-and-finally-15"><span class="toc-item-num">15&nbsp;&nbsp;</span>Errors Handling: try except and finally</a></span></li><li><span><a href="#Memory-Management-in-Python" data-toc-modified-id="Memory-Management-in-Python-16"><span class="toc-item-num">16&nbsp;&nbsp;</span>Memory Management in Python</a></span></li></ul></div>

# Iterations

* if,elif, else Statements
* for Loops
* while Loops
* range() functions
* break and continue statements
* pass statement  
* enumerate
* comprehesions

## if  Statements

* The colon (:)  separates the header of the compound statement from the body.  
* The line after the colon must be indented. It is standard in Python to use four spaces for indenting.    
* All lines indented the same amount after the colon will be executed whenever the BOOLEAN_EXPRESSION is true.   

#Python if Statement Syntax  

`if test expression:
    statement(s)`


```python
if 1 < 2:
    print('One Greater Than Two')
```

```python
# If the number is positive, we print an appropriate message

num = 3
if num > 0:
    print(num, "is a positive number.")
print("This is always printed.")

num = -1
if num > 0:
    print(num, "is a positive number.")
print("This is also always printed.")
```

## if...else Statement

* It is frequently the case that you want one thing to happen when a condition it true, and something else to happen when it is false

# Syntax of if...else

`if test expression:
    Body of if
else:
    Body of else`


```python
if 1 < 2:
    print('first')
else:
    print('last')
```


```python
# Program checks if the number is positive or negative
# And displays an appropriate message

num = 3

# Try these two variations as well. 
# num = -5
# num = 0

if num >= 0:
    print("Positive or Zero")
else:
    print("Negative number")
```

## if...elif...else Statement

#Syntax of if...elif...else

`if test expression:
    Body of if
elif test expression:
    Body of elif
else: 
    Body of else`

**Example of if...elif...else**


```python
if 1 == 2:
    print('first')
elif 3 == 3:
    print('middle')
else:
    print('Last')
```


```python
# In this program, 
# we check if the number is positive or
# negative or zero and 
# display an appropriate message

num = 3.4

# Try these two variations as well:
# num = 0
# num = -4.5

if num > 0:
    print("Positive number")
elif num == 0:
    print("Zero")
else:
    print("Negative number")
```

## Nested if statements

**Python Nested if Example**

**Source Code: Using Nested `if`**


```python
# In this program, we input a number
# check if the number is positive or
# negative or zero and display
# an appropriate message
# This time we use nested if

num = float(input("Enter a number: "))
if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("Positive number")
else:
    print("Negative number")
```

## Practice 

**Python Program to Check if a Number is Positive, Negative or 0**

**Source Code: Using `if...elif...else`**


```python
num = float(input("Enter a number: "))
if num > 0:
   print("Positive number")
elif num == 0:
   print("Zero")
else:
   print("Negative number")
# Here, we have used the if...elif...else statement. We can do the same thing using nested if statements as follows.
```

**Python Program to Check if a Number is Odd or Even**


```python
# Python program to check if the input number is odd or even.
# A number is even if division by 2 give a remainder of 0.
# If remainder is 1, it is odd number.

num = int(input("Enter a number: "))
if (num % 2) == 0:
   print("{0} is Even".format(num))
else:
   print("{0} is Odd".format(num))
```

**Python Program to Check Leap Year**

A leap year is exactly divisible by 4 except for century years (years ending with 00). The century year is a leap year only if it is perfectly divisible by 400. For example,


```python
# Python program to check if the input year is a leap year or not

year = 2000

# To get year (integer input) from the user
# year = int(input("Enter a year: "))

if (year % 4) == 0:
   if (year % 100) == 0:
       if (year % 400) == 0:
           print("{0} is a leap year".format(year))
       else:
           print("{0} is not a leap year".format(year))
   else:
       print("{0} is a leap year".format(year))
else:
   print("{0} is not a leap year".format(year))
```

## Iterables and Iterators

| Function      	| Description                                                             	|
|---------------	|-------------------------------------------------------------------------	|
| `range()`     	| Generates a range of integer values                                     	|
| `enumerate()` 	| Returns a list of tuples containing indices and values from an iterable 	|
| `iter()`      	| Returns an iterator object                                              	|
| `next()`      	| Retrieves the next item from an iterator                                	|



<sub>source: <a href="https://realpython.com/python-data-types/#strings" target="_blank">https://realpython.com/python-data-types/#strings</a></sub>  

## while Loops

* iterate over a block of code as long as the test expression (condition) is true.  
* The while loop can be terminated with a `break` statement.

**Syntax of while Loop in Python**

`while test_expression:
    Body of while`

* In while loop, test expression is checked first. The body of the loop is entered only if the `test_expression` evaluates to `True`. After one iteration, the test expression is checked again. This process continues until the `test_expression` evaluates to `False`.
* Counter is must in while block to iterate the statements


```python
i = 1
while i < 5:
    print('i is: {}'.format(i))
    i = i+1
```


```python
# Program to add natural
# numbers upto 
# sum = 1+2+3+...+n

# To take input from the user,
# n = int(input("Enter n: "))

    n = 10

    # initialize sum and counter
    sum = 0
    i = 1

    while i <= n:
        sum = sum + i
        i = i+1    # update counter

    # print the sum
    print("The sum is", sum)
```

**Ex: While loop using list and get sum**


```python
l = [3,4,7,9,1]
i = 0
sum = 0
while i < len(l):
    sum = sum+l[i]
    i = i+1    # update counter

# print the sum
print("The sum is", sum)
```

**while loop with else**


```python
# Example to illustrate
# the use of else statement
# with the while loop

counter = 0

while counter < 3:
    print("Inside loop")
    counter = counter + 1
else:
    print("Inside else")
```

**Difference between `while` and `IF` **


```python
i = 1
if i < 5: # one time check
    print('i is: {}'.format(i))
    # i = i+1 # manual increment
```

    i is: 1
    


```python
# you will get continuoius infinite values (don't run)
i = 1
while i < 5: # infinite iteration
    print('i is: {}'.format(i))
    # i = i+1 # if we don't provide manual increment
```

## for Loops

The for loop in Python is used to iterate over a sequence (`list, tuple, string`) or other iterable objects. Iterating over a sequence is called traversal.

#syntax:   
`for iterating_var in iterable:
    statement/statements`


```python
seq = [1,2,3,4,5]
```


```python
type(seq)
```


```python
for item in seq:
    print(item)
```


```python
for item in seq:
    print('Yep')
```


```python
for jelly in seq:
    print(jelly+jelly)
```


```python
# Program to find the sum of all numbers stored in a list

# List of numbers
numbers = [6, 5, 3, 8, 4, 2, 5, 4, 11]

# variable to store the sum
sum = 0

# iterate over the list
for val in numbers:
	sum = sum+val

# Output: The sum is 48
print("The sum is", sum)
```


```python
""" Loading the Dishwasher """

# dirty dishes in the sink
sink = ['bowl','plate','cup']

for dish in sink:
    print('Putting {} in the dishwasher'.format(dish))
    sink.remove(dish)

# check that the sink is empty
print(sink)
```

    Putting bowl in the dishwasher
    Putting cup in the dishwasher
    ['plate']
    


```python
""" Loading the Dishwasher """

# dirty dishes in the sink
sink = ['bowl','plate','cup']

for dish in list(sink):
    print('Putting {} in the dishwasher'.format(dish))
    sink.remove(dish)

# check that the sink is empty
print(sink)
```

    Putting bowl in the dishwasher
    Putting plate in the dishwasher
    Putting cup in the dishwasher
    []


**for loop with else**


```python
digits = [0, 1, 5]

for i in digits:
    print(i)
else:
    print("No items left.")
```

**How for loop actually works?**  
https://www.programiz.com/python-programming/iterator#for-loop  

**Difference between iterable and iterator**  
https://www.geeksforgeeks.org/python-difference-iterable-iterator/


```python
# Function to check object 
# is iterable or not  
def iterable(obj): 
    try: 
        iter(obj) 
        return True
          
    except TypeError: 
        return False
  
# Driver Code      
for element in [34, [4, 5], (4, 5), 
             {"a":4}, "dfsdf", 4.5]: 
                   
    print(element, " is iterable : ", iterable(element)) 
```

    34  is iterable :  False
    [4, 5]  is iterable :  True
    (4, 5)  is iterable :  True
    {'a': 4}  is iterable :  True
    dfsdf  is iterable :  True
    4.5  is iterable :  False


## range()

* generate a sequence of numbers using `range()` function. `range(10)` will generate numbers from 0 to 9 (10 numbers).  
* Syntax: `range(start,stop,step size)`
```{py}
range(stop) takes one argument.
range(start, stop) takes two arguments.
range(start, stop, step) takes three arguments.
```


```python
range(5)
```


```python
r = range(5)
r
```




    range(0, 5)



* To force this function to output all the items, we can use the function `list()`.   


```python
list(range(5))
```


```python
list(r)
```




    [0, 1, 2, 3, 4]



**We can use the range() function in for loops to iterate through a sequence of numbers. **


```python
for i in range(5):
    print(i)
```


```python
# Output: range(0, 10)
print(range(10))

# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(range(10)))

# Output: [2, 3, 4, 5, 6, 7]
print(list(range(2, 8)))

# Output: [2, 5, 8, 11, 14, 17]
print(list(range(2, 20, 3)))	
```

**Decrementing With `range()`**


```python
for i in range(10, 4, -2):
    print(i)
```

    10
    8
    6
    


```python
for i in range(10, -6, -2):
    print(i)
```

    10
    8
    6
    4
    2
    0
    -2
    -4


 **It can be combined with the `len()` function to iterate though a sequence using indexing. Here is an example.**


```python
# Program to iterate through a list using indexing

genre = ['pop', 'rock', 'jazz']

# iterate over the list using index
for i in range(len(genre)):
	print("I like", genre[i])
```

## enumerate¶ 

for foo in x loops over the elements of a list and for i in range(len(x)) loops over the indices of a list. What if you want to do both?
   
Enter the enumerate function, one of Python's hidden gems:. 
* `enumerate()` function adds a counter to an iterable  
* a tuple is produced with (`counter`, `element`)  
* `enumerate(iterable, start=0)` start (optional) — enumerate() starts counting from this number. If start is omitted, 0 is taken as the start.  

Given a list, enumerate returns an object which iterates over the indices and the values of the list.
   
(Like the range() function, it returns an iterable object. To see its contents as a list, we can call list() on it.). 


```python
list(enumerate(['a', 'b']))
```




    [(0, 'a'), (1, 'b')]




```python
iterable = [8,-2,13,4]
list(enumerate(iterable, start=2))
```




    [(2, 8), (3, -2), (4, 13), (5, 4)]




```python
iterable = [8,-2,13,4]
list(enumerate(iterable, start=-2))
```




    [(-2, 8), (-1, -2), (0, 13), (1, 4)]




```python
l1 = [10,20,32,45,60]
print(list(enumerate(l1)))
for i, j in enumerate(l1):
    print(i,j)

```

    [(0, 10), (1, 20), (2, 32), (3, 45), (4, 60)]
    0 10
    1 20
    2 32
    3 45
    4 60
    


```python
for item in enumerate('abcd'):
    print(item)
```

    (0, 'a')
    (1, 'b')
    (2, 'c')
    (3, 'd')
    


```python
for i,j in enumerate('abcd'):
    print(i,j)
```

    0 a
    1 b
    2 c
    3 d
    


```python
# multiply 2 for only odd numbers from a given list 
def double_odds(nums):
    for i, num in enumerate(nums):
        if num % 2 == 1:
            nums[i] = num * 2

x = list(range(10))
double_odds(x)
x
```




    [0, 2, 2, 6, 4, 10, 6, 14, 8, 18]



We can use this unpacking syntax any time we iterate over a collection of tuples.


```python
nums = [
    ('one', 1, 'I'),
    ('two', 2, 'II'),
    ('three', 3, 'III'),
    ('four', 4, 'IV'),
]

for word, integer, roman_numeral in nums:
    print(integer, word, roman_numeral, sep=' = ', end='; ')
```

    1 = one = I; 2 = two = II; 3 = three = III; 4 = four = IV; 

## The break statement
* The break statement is used to immediately leave the body of its loop. The next statement to be executed is the first one after the loops body ends 


```python
# Use of break statement inside loop

for val in "string":
    if val == "i":
        break # after this it  exit from the for loop
    print(val)

print("The end")
```


```python
for i in [12, 16, 17, 24, 29]:
    if i % 2 == 1:  # if the number is odd
        break        # immediately exit the loop
    print(i)
print('lucid')
print("done")
```

    12
    16
    lucid
    done


## The continue statement
* This is a control flow statement that causes the program to immediately skip the processing of the rest of the body of the loop, for the current iteration. But the loop still carries on running for its remaining iterations(**continue = skip this and go next**):


```python
# Program to show the use of continue statement inside loops

for val in "string":
    if val == "i":
        continue
    print(val)

print("The end")
```


```python
for i in [12, 16, 17, 24, 29, 30]:
    if i % 2 == 1:      # if the number is odd
        continue        # don't process it
    print(i)
print("done")
```

    12
    16
    24
    30
    done


## Python pass statement

* In Python programming, pass is a null statement, it results into no operation (NOP).

**Example: pass Statement**



```python
# pass is just a placeholder for
# functionality to be added later.
sequence = {'p', 'a', 's', 's'}
for val in sequence:
    pass
```

## Comprehensions

* for faster execution
* shorter and effective codes (single line)
* involves 3 things – iteration, conditional filtering and processing. 

#Syntax of List Comprehension

`[ expression for item in iterable ]` or `[expression for item in list]`

### comprehension for lists

![Imgur](https://i.imgur.com/IeRiWWl.png)


```python
h_letters = [letter for letter in 'human' ]
print( h_letters)
```

    ['h', 'u', 'm', 'a', 'n']
    


```python
lst = [i for i in range(11)]
print(lst)
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    


```python
squares = [x * x for x in range(10)]
print(squares)
```

    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
    


```python
cube_list = [i**3 for i in range(50, 101)]
print(cube_list)
```

    [125000, 132651, 140608, 148877, 157464, 166375, 175616, 185193, 195112, 205379, 216000, 226981, 238328, 250047, 262144, 274625, 287496, 300763, 314432, 328509, 343000, 357911, 373248, 389017, 405224, 421875, 438976, 456533, 474552, 493039, 512000, 531441, 551368, 571787, 592704, 614125, 636056, 658503, 681472, 704969, 729000, 753571, 778688, 804357, 830584, 857375, 884736, 912673, 941192, 970299, 1000000]


**IF condition With List Comprehension**

#Syntax of List Comprehension  
`[ expression for item in iterable if condition ] `


```python
even_squres = [x * x for x in range(10) if x % 2 == 0]
print(even_squres)
```

    [0, 4, 16, 36, 64]
    


```python
[x for x in 'MATHEMATICS' if x in ['A','E','I','O','U']]
```




    ['A', 'E', 'A', 'I']




```python
cart_1 = [1, 8, 29, 34, 58, 74, 88, 99]
cart_2 = [3, 8, 31, 36, 58, 77, 88, 93]
# List comprehension version
cashier_5 = [item for item in cart_1 if item in cart_2]
cashier_5
```




    [8, 58, 88]



**Nested IF with List Comprehension**


```python
num_list = [y for y in range(100) if y % 2 == 0 if y % 5 == 0]
print(num_list)
```

    [0, 10, 20, 30, 40, 50, 60, 70, 80, 90]


**nested for loop**


```python
print ([x+y for x in 'get' for y in 'set' if x != 't' and y != 'e' ])
```

    ['gs', 'gt', 'es', 'et']


**if...else With List Comprehension**


```python
obj = ["Even" if i%2==0 else "Odd" for i in range(10)]
print(obj)
```

    ['Even', 'Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even', 'Odd']


**Nested List Comprehensions**


```python

list_of_list = [[1,2,3],[4,5,6],[7,8]]

# Flatten `list_of_list`
[y for x in list_of_list for y in x]

```




    [1, 2, 3, 4, 5, 6, 7, 8]



### comprehension for dictionaries


```python
squares3_dict = {i: i**2 for i in range(30) if i % 3 == 0}
squares3_dict
```




    {0: 0,
     3: 9,
     6: 36,
     9: 81,
     12: 144,
     15: 225,
     18: 324,
     21: 441,
     24: 576,
     27: 729}




```python
capitals = {'United States': 'Washington, DC','France': 'Paris','Italy': 'Rome'}
capitals_bycapital = {capitals[key]: key for key in capitals}
capitals_bycapital
```




    {'Paris': 'France', 'Rome': 'Italy', 'Washington, DC': 'United States'}



### comprehension for sets

* Set comprehensions are created in much the same way as dictionary comprehensions. 


```python
# You can create a normal set like this:
my_list = [1, 2, 2, 3, 4, 5, 5, 7, 8]
my_set = set(my_list)
my_set
```




    {1, 2, 3, 4, 5, 7, 8}




```python
# Now let’s rewrite this code to use a set comprehension:
my_list = [1, 2, 2, 3, 4, 5, 5, 7, 8]
my_set = {x for x in my_list}  # uses the curly braces that the dictionary comprehension has.
my_set  
```




    {1, 2, 3, 4, 5, 7, 8}



## Errors Handling: try except and finally

**Types of Errors**
* Syntax Errors
* Runtime Errors
* Logic Errors

```
#Syntax Errors
x = 42
y = 206 
if x == y
    print('Equal')
```

```{python}
#Runtime Errors
x = 42
y = 0
print(x/y)
```


```python
# once we execute the below script we will encounter an error
print(10/0)
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-1-364d6fd1cf4d> in <module>()
          1 # once we execute the below script we will encounter an error
    ----> 2 print(10/0)
    

    ZeroDivisionError: division by zero


```{python}
#Logic Errors
x = 206
y = 42
if x<y:
    print(str(x) + 'is greater than' + str(y))
```


```python
# we didn't get desired output
x = 206
y = 42
if x<y:
    print(str(x) + 'is greater than' + str(y))
```

* To overcome this error we can tell python to handle this error and throw some message when ever it happens otherwise execute succesfully*


```python
try:
    print(10/0)
except:
    print("Can't divide a number by zero")
    
```

    Can't divide a number by zero
    


```python
try:
    print(10/2)
except:
    print("Can't divide a number by zero")
```

    5.0


**Handling Exceptions with Try/Except/Finally**


```python
     try:
...     print("in the try block")
...     print(1/0)                   # You put the unsafe code in the try: block. 
... except:
...     print("In the except block") # You put the fall-back code in the Except: block
... finally:
...     print("In the finally block") # The final code is kept in the Finally: block
...
```

    in the try block
    In the except block
    In the finally block


**Raising exceptions for a predefined condition**  
For example, if you want to limit the user-input to only positive integers, raise an exception.


```python
try:
    user = int(input('Please enter a number? '))
    if user < 0:
        raise ValueError("please give positive number")
    else:
        print("user input: %s" % user)
except ValueError as e:
    print(e)
```

    Please enter a number? 15
    user input: 15


<br/>
## Memory Management in Python

 Memory management in Python involves a private heap containing all Python objects and data structures. Interpreter takes care of Python heap and that the programmer has no access to it.
- The allocation of heap space for Python objects is done by Python memory manager. The core API of Python provides some tools for the programmer to code reliable and more robust program.
- Python also has a build-in garbage collector which recycles all the unused memory. When an object is no longer referenced by the program, the heap space it occupies can be freed. The garbage collector determines objects which are no longer referenced by the sprogram frees the occupied memory and make it available to the heap space.


```python
x  =10
print(type(x))

y = x
if (id(x) == id(y)):
    print("x and y refer to same object")

x = x+1
if (id(x) != id(y)):
    print("x and y refer to different object")
    
z = 10
if (id(y) == id(z)):
    print("y and z point to the same object")
else:
    print("y and z point to different same object")
```

    <class 'int'>
    x and y refer to same object
    x and y refer to different object
    y and z point to the same object


**Reason:**  
Everything is object in Python  
Python optimizes memory unilization by allocating the same oject reference to a new variable if object already exiists with same value

<br/>
**Comparison with Other Languages:**
<br/>
![Imgur](https://i.imgur.com/Q69apaJ.jpg)
<sub>source: <a href="https://www.youtube.com/watch?v=arxWaw-E8QQ" target="_blank">https://www.youtube.com/watch?v=arxWaw-E8QQ</a></sub>  


<span style="color:red; font-family:Comic Sans MS">Sources & References</span>  
<a href="https://www.programiz.com" target="_blank">https://www.programiz.com</a>  
<a href="http://www.openbookproject.net/books/bpp4awd/ch04.html" target="_blank">http://www.openbookproject.net/books/bpp4awd/ch04.html</a>  

<span style="color:red; font-family:Comic Sans MS">Further Resources</span>  
https://www.geeksforgeeks.org/loops-in-python/  
