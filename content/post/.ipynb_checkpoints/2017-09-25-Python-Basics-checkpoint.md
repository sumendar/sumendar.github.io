---
title: Python-Basics
author: sumendar
date: '2017-09-25'
slug: Python-Basics
categories: ['python', 'blogdown']
tags: ['basics']
subtitle: 'subtitle'
---

In this blog post we will be going to discuss about python basics
  
Python is multi-purpose programming language developed by Guido van Rossum.
  
The language has  easy-to-use syntax, it's a perfect language for someone trying to learn any programming for the first time.
  
This is a comprehensive guide on Basic fundamentals concepts which we are keep in mind before writing code.
  
<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Basics" data-toc-modified-id="Basics-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Basics</a></span><ul class="toc-item"><li><span><a href="#print()-function:" data-toc-modified-id="print()-function:-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span><code>print()</code> function:</a></span></li><li><span><a href="#comment-with-#-symbol:" data-toc-modified-id="comment-with-#-symbol:-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>comment with <code>#</code> symbol:</a></span></li></ul></li><li><span><a href="#Operators" data-toc-modified-id="Operators-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Operators</a></span></li><li><span><a href="#Primitive-Data-Types" data-toc-modified-id="Primitive-Data-Types-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Primitive Data Types</a></span><ul class="toc-item"><li><span><a href="#Booleans" data-toc-modified-id="Booleans-3.1"><span class="toc-item-num">3.1&nbsp;&nbsp;</span>Booleans</a></span></li><li><span><a href="#Numbers" data-toc-modified-id="Numbers-3.2"><span class="toc-item-num">3.2&nbsp;&nbsp;</span>Numbers</a></span><ul class="toc-item"><li><span><a href="#integer" data-toc-modified-id="integer-3.2.1"><span class="toc-item-num">3.2.1&nbsp;&nbsp;</span>integer</a></span></li><li><span><a href="#float" data-toc-modified-id="float-3.2.2"><span class="toc-item-num">3.2.2&nbsp;&nbsp;</span>float</a></span></li><li><span><a href="#complex" data-toc-modified-id="complex-3.2.3"><span class="toc-item-num">3.2.3&nbsp;&nbsp;</span>complex</a></span></li></ul></li><li><span><a href="#Strings" data-toc-modified-id="Strings-3.3"><span class="toc-item-num">3.3&nbsp;&nbsp;</span>Strings</a></span></li><li><span><a href="#Date-and-Time" data-toc-modified-id="Date-and-Time-3.4"><span class="toc-item-num">3.4&nbsp;&nbsp;</span>Date and Time</a></span></li></ul></li><li><span><a href="#Data-Structures" data-toc-modified-id="Data-Structures-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>Data Structures</a></span><ul class="toc-item"><li><span><a href="#Composite-Data-Types" data-toc-modified-id="Composite-Data-Types-4.1"><span class="toc-item-num">4.1&nbsp;&nbsp;</span>Composite Data Types</a></span><ul class="toc-item"><li><span><a href="#Lists" data-toc-modified-id="Lists-4.1.1"><span class="toc-item-num">4.1.1&nbsp;&nbsp;</span>Lists</a></span></li><li><span><a href="#Tuples" data-toc-modified-id="Tuples-4.1.2"><span class="toc-item-num">4.1.2&nbsp;&nbsp;</span>Tuples</a></span></li></ul></li><li><span><a href="#Collection-data-types" data-toc-modified-id="Collection-data-types-4.2"><span class="toc-item-num">4.2&nbsp;&nbsp;</span>Collection data types</a></span><ul class="toc-item"><li><span><a href="#Dictionaries" data-toc-modified-id="Dictionaries-4.2.1"><span class="toc-item-num">4.2.1&nbsp;&nbsp;</span>Dictionaries</a></span></li><li><span><a href="#Sets" data-toc-modified-id="Sets-4.2.2"><span class="toc-item-num">4.2.2&nbsp;&nbsp;</span>Sets</a></span></li></ul></li></ul></li><li><span><a href="#Data-types-Tree" data-toc-modified-id="Data-types-Tree-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>Data types Tree</a></span></li><li><span><a href="#Queues(FIFO)-and-Stacks(LIFO)" data-toc-modified-id="Queues(FIFO)-and-Stacks(LIFO)-6"><span class="toc-item-num">6&nbsp;&nbsp;</span>Queues(FIFO) and Stacks(LIFO)</a></span></li><li><span><a href="#Type-conversion" data-toc-modified-id="Type-conversion-7"><span class="toc-item-num">7&nbsp;&nbsp;</span>Type conversion</a></span><ul class="toc-item"><li><span><a href="#Implicit-type-conversion" data-toc-modified-id="Implicit-type-conversion-7.1"><span class="toc-item-num">7.1&nbsp;&nbsp;</span>Implicit type conversion</a></span></li><li><span><a href="#Explicit-type-conversion" data-toc-modified-id="Explicit-type-conversion-7.2"><span class="toc-item-num">7.2&nbsp;&nbsp;</span>Explicit type conversion</a></span></li></ul></li></ul></div>

## Basics

### `print()` function:


```python
print('hello world')
```

```python
lst = list(a=c(3,5,1,-8,8,90),b=matrix(1:12,4,3))
print(lst) # print list
```

    hello world
    


```python
print("hello", 'world')
```

    hello world
    


```python
print("hello world" + "!")
```

    hello world!
    


```python
print("welcome", "to", "python", sep="_", end=";")
```

    welcome_to_python;


```python
print("welcome", "to", "python", sep="_", end=";")
print("data science")
```

    welcome_to_python;data science
    


```python
print("welcome", "to", "python", sep="_", end="\n") # end with new line(by default)
print("data science")
```

    welcome_to_python
    data science


### comment with `#` symbol: 


```python
# this statement will print the statement inside in it
print("welcome to data science")
```

    welcome to data science


Python has many native datatypes. Here are the important ones:

* Booleans are either True or False.
* Numbers can be integers (1 and 2), floats (1.1 and 1.2), fractions (1/2 and 2/3), or even complex numbers.
* Strings are sequences of Unicode characters, e.g. an html document.
* Lists are ordered sequences of values.
* Dictionaries are unordered bags of key-value pairs.
* Tuples are ordered, sequences of values and immutable (cannot be modified inplace)
* Sets are unordered bags of values.

## Operators

| Operators (Decreasing order of precedence) | Operators (Decreasing order of precedence)        |
|--------------------------------------------|---------------------------------------------------|
| `**`                                       | Exponent                                          |
| `+, -, *, /, //, %`                        | Addition, Subtraction, Multiplication, Division, Floor division, Modulus |
| `< > <= >= == !=`                          | Comparison operators                              |
| `= %= /= //= -= += *= **=`                 | Assignment Operators                              |
| `is is not`                                | Identity operators                                |
| `in not in`                                | Membership operators                              |
| `not or and`                               | Logical operators                                 |

<span style="color:red; font-family:centurygothic ">Continue...</span><a href="https://www.guru99.com/python-operators-complete-tutorial.html" target="_blank">https://www.guru99.com/python-operators-complete-tutorial.html</a>  

## Primitive Data Types

### Booleans


```python
t = True
```


```python
type(t)
```




    bool




```python
False
```




    False



### Numbers

#### integer


```python
i = 4 
type(i)
```




    int



#### float


```python
f = 3.45 
type(f)
```




    float



#### complex


```python
cmp = 3+4j
type(cmp)
```




    complex




```python
cmp.real
```




    3.0




```python
cmp.imag
```




    4.0




```python
1 + 1
```




    2




```python
1 * 3
```




    3




```python
1 / 2
```




    0.5




```python
print(7+8)
print(4*6)
2 ** 4
```

    15
    24
    




    16




```python
4 % 2
```




    0




```python
5 % 2
```




    1




```python
(2 + 3) * (5 + 5)
```




    50



**Number Calculations**  
(Operator Precedence)  

* PEMDAS(parenthesis, exponents, multiplication, division, addition, subtraction)


```python
3+3/3
```




    4.0




```python
(3+3)/3
```




    2.0




```python
((((13+5)*2)-4)/2)-13
# How did that happen? Let’s work it out.
# 13+5 gives us 18
# 18*2 gives us 36
# 36-4 gives us 32
# 32/2 gives us 16.0 #Note that division gives us floats!
# 16-13 gives us 3.0
```




    3.0



https://data-flair.training/blogs/python-operator-precedence/

### Strings

* string is a ordered sequence of characters. 
* A string is contained within two quotes or single quotes. 
* A string can be spaces or digits. 
* A string can also be special characters. 
* Positive / Negative indexing applicable
* Strings are immutable(we cannot change inplace but we can create another string from it)


```python
st = 'data science and machine learning with python'
```


```python
type(st)
```




    str



**Indexing:**


```python
# positive indexing
print(st[0])
print(st[1])
print(st[2])
```

    d
    a
    t
    


```python
# negative indexing
print(st[-1])
print(st[-2])
print(st[-3])
```

    n
    o
    h


**Slicing:**


```python
print(st[0:4])
print(st[:4])
print(st[4:])
print(st[5:9])
print(st[::2]) # step 2
print(st[::3]) # step 2
print(st[2:12:4]) # 
print(st[::-1])  # reverse the string
print(st[::-2])  # reverse the string with step 1
```

    data
    data
     science and machine learning with python
    scie
    dt cec n ahn erigwt yhn
    dacn dai ai tph
    tcc
    nohtyp htiw gninrael enihcam dna ecneics atad
    nhy twgire nha n cec td


**String Methods:**


```python
s= "hello world" # using double quotes
```


```python
s= 'hello world' # using single quotes
```


```python
# Multi-line Strings
to_you = """Stranger, if you passing meet me and desire to speak to me, why
  should you not speak to me?
And why should I not speak to you?"""

print(to_you)
```

    Stranger, if you passing meet me and desire to speak to me, why
      should you not speak to me?
    And why should I not speak to you?
    


```python
s.index('d')
```




    10




```python
s.capitalize()
```




    'Hello world'




```python
s.count('o')
```




    2




```python
value = "cat ppicture is cat picture"

# Find first index of this string.
i = value.find("p")
print(i)

# Find first index (of this string) after previous index.
b = value.find("p", i + 1)
print(b)


b = value.find("p", i + 2)
print(b)
```

    4
    5
    20


The `index()` method is similar to `find()` method for strings. The only difference is that `find()` method returns -1 if the substring is not found, whereas `index()` throws an exception.


```python
s.title()
```




    'Hello World'




```python
s.upper()
```




    'HELLO WORLD'




```python
s.islower()
```




    True




```python
s= "HELLO WORLD"
```


```python
s.islower()
```




    False




```python
s.capitalize()
```




    'Hello world'




```python
s.lower()
```




    'hello world'




```python
s = "HeLlO WoRlD"
```


```python
s.swapcase()
```




    'hElLo wOrLd'




```python
s = " Hello world how are you "
```


```python
s = "hello world how are you"
```


```python
s.capitalize()
```




    'Hello world how are you'




```python
s.title()
```




    'Hello World How Are You'




```python
s.upper()
```




    'HELLO WORLD HOW ARE YOU'




```python
"H" in s
```




    False




```python
"h" in s
```




    True




```python
len(s)
```




    11




```python
s = ' hello world how are you'
```


```python
s.strip()
```




    'hello world how are you'




```python
min(s.strip())
```




    ' '




```python
max(s)
```




    'y'




```python
s
```




    ' hello world how are you'




```python
s.isspace()
```




    False




```python
s.strip()
```




    'hello world how are you'



**strings immutable nature **


`my_string = "abc"`  
`my_string[0] = "d"`  
```{py}
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-1-f26f28798517> in <module>()
      1 my_string = "abc"
----> 2 my_string[0] = "d"

TypeError: 'str' object does not support item assignment
```

*strings are immutable, which means you can't change an existing string (inplace). The best you can do is create a new string that is a variation on the original:*


```python
greeting = 'Hello, world!'
new_greeting = 'J' + greeting[1:]
print(new_greeting)
print(greeting)
```

    Jello, world!
    Hello, world!


**String.format()**  


```python
name = "sumendar"
greeting = "My name is {}".format(name)
greeting
```




    'My name is sumendar'



**String concatenation**


```python
print("happy" + " " + "birthday")
print("my name is " + "john")
```

    happy birthday
    my name is john


**Escape Sequences in Strings**

* backslash (\) character is used in some strings to be treated one or more characters specially. 
* This is referred to as an escape sequence, because `the backslash causes the subsequent character sequence to “escape”` its usual meaning.


```python
print('This string contains a single quote (') character.')
# gives a syntaxError
```


      File "<ipython-input-8-4fb72c6c5730>", line 1
        print('This string contains a single quote (') character.')
                                                               ^
    SyntaxError: invalid syntax
    



```python
print('This string contains a single quote (\') character.')
print("This string contains a double quote (\") character.")
```

    This string contains a single quote (') character.
    This string contains a double quote (") character.
    


```python
print('a,
      b,
      c)    # if we press Enter will gives SyntaxError after each letter
```


      File "<ipython-input-11-06aeb0cb83d6>", line 1
        print('a,
                 ^
    SyntaxError: EOL while scanning string literal
    



```python
print('a\
b\
c')

print('a\
b\
c')
```

    abc
    abc
    


```python
print('foo\\bar') # o include a literal backslash in a string, escape it with a backslash
```

    foo\bar
    


```python
print(r'foo\bar') # o include a literal backslash in a string, escape it with a letter r 
```

    foo\bar


**Applying Special Meaning to Characters**


```python
print('foo\tbar')
print("a\tb")
print("a\141\x61")
print("a\nb")
print('\u2192 \N{rightwards arrow}')
```

    foo	bar
    a	b
    aaa
    a
    b
    → →


**Raw Strings**

* A raw string literal is preceded by r or R.  
* Escape sequences in the associated string are not translated. The backslash character is left in the string:


```python
print('foo\nbar')
```

    foo
    bar
    


```python
print(r'foo\nbar')
```

    foo\nbar
    


```python
print('foo\\bar')
```

    foo\bar
    


```python
print(r'foo\\bar')
```

    foo\\bar


**Triple-Quoted Strings**

* Escape sequences still work in triple-quoted strings, but single quotes, double quotes, and newlines can be included without escaping them. 
* This provides a convenient way to create a string with both single and double quotes in it:


```python
print('''This string has a single (') and a double (") quote.''')
```

    This string has a single (') and a double (") quote.
    


```python
print("""This is a
string that spans
across several lines""")
# this also allows for multiline strings:
```

    This is a
    string that spans
    across several lines


https://towardsdatascience.com/useful-string-methods-in-python-5047ea4d3f90  

**Python Syntax:**  
https://www.codecademy.com/learn/learn-python-3/modules/learn-python3-syntax/reference  

### Date and Time

A date in Python is not a data type of its own, but we can import a module named datetime to work with dates as date objects.


```python
import datetime

x = datetime.datetime.now()
print(x)
```

    2019-03-07 10:33:50.931781
    


```python
print(x.year)
```

    2019
    


```python
# strftime is a method for formatting date objects into readable strings.
print(x.strftime("%A"))
# it takes one parameter called format
# http://strftime.org/
```

    Thursday
    


```python
# Create a date object
x = datetime.datetime(2020, 5, 17)
print(x)
```

    2020-05-17 00:00:00


https://www.guru99.com/date-time-and-datetime-classes-in-python.html  
https://dzone.com/articles/python-101-working-with-dates-and-time  

## Data Structures 
(Non-primitive data structures)

Non-primitive types are the sophisticated members of the data structure family. They don't just store a value, but rather a collection of values in various formats.

### Composite Data Types

#### Lists

* General purpose
* Most widely used data structures
* contain any type of objects
* similar to arrays
* can be extended or reduce the size as we needed
* Sequence type
* sortable
* declare them using square brackets separated with commas of each value/item
* Better to use this object for list of values which we need some flexibility to add/remove/sort/reverse/delete...etc operations.

> **Example:** 
* List of employees in your department
* List of stocks you want to analyze
A = [ ] # This is a blank list variable
B = [1, 23, 45, 67] # this list creates an initial list of 4 numbers.
C = [2, 4, 'john'] # lists can contain different variable types.

```python
[1,2,3]
```




    [1, 2, 3]




```python
['hi',1,[1,2]]
```




    ['hi', 1, [1, 2]]




```python
my_list = ['a','b','c']
```


```python
my_list.append('d')
```


```python
my_list
```




    ['a', 'b', 'c', 'd']




```python
my_list[0]
```




    'a'




```python
my_list[1]
```




    'b'




```python
my_list[1:]
```




    ['b', 'c', 'd']




```python
my_list[:1]
```




    ['a']




```python
my_list[0] = 'NEW'
```


```python
my_list
```




    ['NEW', 'b', 'c', 'd']




```python
mylist = ['Rhino', 'Grasshopper', 'Flamingo', 'Bongo']
B = len(mylist) # This will return the length of the list which is 3. The index is 0, 1, 2, 3.
print (mylist[1]) # This will return the value at index 1, which is 'Grasshopper'
print (mylist[0:2]) # This will return the first 2 elements in the list.
```

    Grasshopper
    ['Rhino', 'Grasshopper']
    


```python
nest = [1,2,3,[4,5,['target']]]
```


```python
nest[3]
```




    [4, 5, ['target']]




```python
nest[3][2]
```




    ['target']




```python
nest[3][2][0]
```




    'target'



nest[3][2][0].upper()


```python
# assign data to a specific element of the list using an index into the list.
mylist = [0, 1, 2, 3]
mylist[0] = 'Rhino'
mylist[1] = 'Grasshopper'
mylist[2] = 'Flamingo'
mylist[3] = 'Bongo'
print (mylist[1])
```

    Grasshopper


The + operator concatenates lists:


```python
a = [1, 2, 3]
b = [4, 5, 6]
c = a + b  # 
print(c)
```

    [1, 2, 3, 4, 5, 6]


Similarly, the * operator repeats a list a given number of times:


```python
 
[0] * 4
```




    [0, 0, 0, 0]




```python
[1, 2, 3] * 3  # The first example repeats [0] four times. The second example repeats the list [1, 2, 3] three times.
```




    [1, 2, 3, 1, 2, 3, 1, 2, 3]



**The Difference Between “is” and “==” in Python**


```python
a = 'banana'
b = 'banana'
a is b
```




    True




```python
a = [1, 2, 3]
b = [1, 2, 3]
a is b
```




    False



**What does [::-1} do?**


```python
l = [1,2,3,4,5]
l[::-1] # reverse the order of list
```




    [5, 4, 3, 2, 1]



follow along:  https://dbader.org/blog/difference-between-is-and-equals-in-python  
https://medium.com/@tyastropheus/tricky-python-i-memory-management-for-mutable-immutable-objects-21507d1e5b95  

**Built-in Functions with List**


| Function    | Description                                                                                       |
|-------------|---------------------------------------------------------------------------------------------------|
| any()       | Return True if any element of the list is true. If the list is empty, return False.               |
| all()       | Returns `True` if all elements of an iterable are true                  	                      |
| len()       |   Return the length (the number of items) in the list.                                            |
| list()      | Convert an iterable (tuple, string, set, dictionary) to a list.                                   |
| max()       | Return the largest item in the list.                                                              |
| min()       | Return the smallest item in the list                                                              |
| sorted()    |   Return a new sorted list (does not sort the list itself).                                       |
| reversed()  | Returns a reverse iterator                                              	|                     
| sum()       | Return the sum of all elements in the list.                                                       |


```python
x = [True, True, False]
if any(x):
    print("At least one True")
if all(x):
    print("Not one False")
if any(x) and not all(x):    
    print("At least one True and one False")
```

    At least one True
    At least one True and one False


**Python list Methods**

| Methods       | Functions                                                |
|---------------|----------------------------------------------------------|
| append()      | to add element to the end of the list                    |
| extend()      | to extend all elements of a list to the another list     |
| insert()      | to insert an element at the another index                |
| remove()      | to remove an element from the list                       |
| pop()         | to remove elements return element at the given index     |
| clear()       | to remove all elements from the list                     |
| index()       | to return the index of the first matched element         |
| count()       | to count of number of elements passed as an argument     |
| sort()        | to sort the elements in ascending order by default       |
| reverse()     | to reverse order element in a list                       |
| copy()        | to return a copy of elements in a list                   |

**`copy()` method vs direct assignment**


```python
l1 = [1,2,3,4]
l2 = l1
print(id(l1))
print(id(l2))
```

    140488771147336
    140488771147336
    


```python
l1.append(999)
print(l2)
```

    [1, 2, 3, 4, 999]
    


```python
l1 = [1,2,3,4]
l2 = l1.copy()
print(id(l1))
print(id(l2))
```

    140488767397832
    140488771825864
    


```python
l1.append(999)
print(l2)
```

    [1, 2, 3, 4]


https://developers.google.com/edu/python/lists  
http://thepythonguru.com/python-lists/  
https://www.tutorialspoint.com/python/python_lists.htm

#### Tuples

* Immutable (we cannot change its content after creation)
* Better for fixed data
* useful to share the data with someone but not allow them to manipulate
* use the data values for arithmatic operations, however the changes is not reflected in the original data
* contain any type of objects (heterogeneous container for items) 
* similar to arrays
* faster compare with the lists
* sequencey type
* To declare tuples we use parentheses.
* Unlike Python lists, tuples does not have methods such as `append()`, `remove()`, `extend()`, `insert()` and `pop()` due to its immutable nature. However, there are many other built-in methods to work with tuple 
* Better to use this object for a list of values which order really matters when there is no need to add/delete those items

> **Example:** 
* List of months, or weekdays..etc
* List of top 10 sales regions in a quarter


```python
t = (1,2,3)
```

t[0]

`t[0] = 'NEW' # not mutable for tuples`
```{python}
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-212-9650bd97cc9a> in <module>()
----> 1 t[0] = 'NEW' # not mutable for tuples

TypeError: 'tuple' object does not support item assignment
```


```python
# real world example
# works better in spyder tool
""" Where's My Mouse? """
import tkinter

def mouse_click(event):

    # retrieve XY coords as a tuple
    coords = root.winfo_pointerxy()
    print('coords: {}'.format(coords))
    print('X: {}'.format(coords[0]))
    print('Y: {}'.format(coords[1]))
    print(type(coords))

root = tkinter.Tk()
root.bind('<Button>', mouse_click)
root.mainloop()
```

https://data-flair.training/blogs/python-tuples-syntax-examples/   
http://thepythonguru.com/python-tuples/  

### Collection data types

#### Dictionaries

* Each item is a pair of a key and value
* It holds word-meaning pairs just like real dictionaries 
* Un ordered
* Dictionaries are not sorted
* Access to the list of keys or values independently.
* To declare a dictionary, we use curly braces.
* Better to use this object for unordered storage of values which are associated with some keys 

> **Examples:** 
* Employee name associated with Employee ID   
* Order status of online food


```python
room_num = {'john': 425, 'tom': 212}
room_num['john'] = 645  # set the value associated with the 'john' key to 645
```


```python
print(room_num)
```

    {'tom': 212, 'john': 645}
    


```python
room_num['james'] = 925
```


```python
print(room_num)
```

    {'james': 925, 'tom': 212, 'john': 645}
    


```python
room_num.keys()
```




    dict_keys(['james', 'tom', 'john'])




```python
room_num.values()

```




    dict_values([925, 212, 645])




```python
room_num.items()
```




    dict_items([('james', 925), ('tom', 212), ('john', 645)])




```python
room_num.pop('james') # takes key as parameter and return corresponding value 
```




    925




```python
room_num
```




    {'john': 645, 'tom': 212}




```python
room_num.popitem() # doesn't take any parameter and gives some arbitrary element as (key, value) tuple 
```




    ('tom', 212)




```python
room_num
```




    {'john': 645}




```python
room_num['isaac'] = 345 # Add a new key 'isaac' with the associated value
print (room_num.keys()) # print out a list of keys in the dictionary
print ('isaac' in room_num) # test to asee if 'issac' is in the dictionary.  This returns true.
```

    dict_keys(['isaac', 'john'])
    True
    


```python
d = {'key1':'value1','key2':'value2'}
```


```python
d
```




    {'key1': 'item1', 'key2': 'item2'}




```python
d['key1']
```




    'item1'



https://www.tutorialspoint.com/python/python_dictionary.htm  
http://thepythonguru.com/python-dictionaries/    
https://realpython.com/python-dicts/    

#### Sets

* Python set is much like a mathematical set theory in that it has well-defined collection of distinct objects
* The objects of a set are called its “elements”.
* Sets are unordered collections of unique elements. Duplicates are not allowed.
* very fast access vs lists
* A set itself may be modified, but the elements contained in the set must be of an immutable type (eg. it might be a tuple but not a list type).
* Python provides us with a list of functions and methods like `discard()`, `pop()`, `clear()`, `remove()`, `add()`, and more. Functions like `len()` and `max()` also apply on sets.
* It is sequenced (automatically while printing), but does not support indexing.
* To declare a set, write a sequence of items separated with commas, inside curly braces.
* Better to use this object a collection of sets which needs to membership or mapping really matters


```python
{1,2,3}
```




    {1, 2, 3}



**Adding Elements to a Set**  
* sets are mutable – but since they are unordered, indexes would not make any sense to it. We will not be able to access or update an element based on the index of an element in a set, as set does not support both indexing and slicing.   
* we can use the `add()` method to add a single element if we need to add more than one element to a set, we can use the `update()` method


```python
# creating a set
a = {1, 3, 5, 7, 11, 13}
b = set([1, 3, 5, 7, 11, 13])
```

**Set Operations on Sets**

* Union
* Intersection
* Difference
* Symmetric Difference


```python
# Union
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}
print ( A | B)
```

    {1, 2, 3, 4, 5, 6}
    


```python
# Intersection
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}
print ( A & B )
```

    {3, 4}
    


```python
# Difference
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}
print(A - B)
```

    {1, 2, 3}
    


```python
# Symmetric Difference
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}
print(A ^ B)
```

    {1, 2, 3, 6, 7, 8}


**Adding element/s to a set**


```python
a.add(8)
print(a)
b.update([5,2,14,7])
print(b)
```

    {1, 3, 5, 7, 8, 11, 13}
    {1, 2, 3, 5, 7, 11, 13, 14}
    


```python
# initialize my_set
my_set = {1,3}
print(my_set)

# add list and set
# Output: {1, 2, 3, 4, 5, 6, 8}
my_set.update([4,5], {1,6,8})
print(my_set)

# if you uncomment below line
# you will get an error
# TypeError: 'set' object does not support indexing

#my_set[0]
```

    {1, 3}
    {1, 3, 4, 5, 6, 8}


**Remove Elements From a Set**

`discard()`    
This method takes the item to delete as an argument.
* deleting an item that doesn’t exist in the set, discard() ignores it


```python
num = {13,12,21,43,16,25}
```


```python
num.discard(3)
```


```python
num
```




    {12, 13, 16, 21, 25, 43}



`remove()`

Like the discard() method, remove() deletes an item from the set.
* deleting an item that doesn’t exist in the set, remove() gives an error


```python
num.remove(5)
```


```python
num
```




    {1, 2, 4, 6}



`pop()`
* here, it does not take an argument. Because a set doesn’t support indexing
* it pops out an arbitrary item. 
* we will not be able to determine which element of the set will be removed using the `pop()` method. In case of list, the last element of the list gets popped when the pop() method is used. 


```python
num = {13,12,21,43,16,25}
```


```python
num.pop()
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-21-03a12495f7f5> in <module>()
    ----> 1 num.pop()
    

    KeyError: 'pop from an empty set'


We can also remove all items from a set using `clear()`.

`clear()`
* It empties the set in Python.


```python
num = {13,12,21,43,16,25}
```


```python
num.clear()
```


```python
num
```




    set()



**frozensets**  
(creating immutable sets)  


```python
S = frozenset([1,2,3])
print(S)
```

    frozenset({1, 2, 3})


https://realpython.com/python-sets/  
https://www.programiz.com/python-programming/set  
https://stackabuse.com/sets-in-python/  

## Data types Tree

![Imgur](https://i.imgur.com/VXwzhyT.jpg)

## Queues(FIFO) and Stacks(LIFO)


```python
""" A Queue of Groceries to Put Away """
# queue is a not built-in datatype
# create a new queue object
import queue 
q = queue.Queue() # create a new object by calling new Queue() custroctor
print(q.empty())

# put bags into the queue
q.put('bag1')
print(q.empty())
q.put('bag2')
q.put('bag3')

# get bags from the queue in FIFO order
print(q.get())
print(q.get())
print(q.get())
# q.get() # causes an error: blocking method, the program will wait until method completes before continuiing execution
# (restart the shell) 

# create a new queue to hold two items
q = queue.Queue(2)
print(q.empty())

# put two bags into the two-item queue
q.put('bag1')
print(q.full())
q.put('bag2')
print(q.full())

# try to put an extra bag into the queue
q.put_nowait('bag3') # causes an error

```


```python
""" A Stack of Bills to Pay """
# python doesn't has built-n stack module, we can use list instead
# create a list to use as the stack
stack = list()

# add some bills to the stack
stack.append('bill1')
stack.append('bill2')

# remove the top bill to pay it
print(stack.pop())

# add two more bills to the stack
stack.append('bill3')
stack.append('bill4')

# remove bills from top to bottom
print(stack.pop())
print(stack.pop())
print(stack.pop())
stack.pop() # causes Indexerror exception

```

## Type conversion

### Implicit type conversion


```python
int1 = 4
float1 = int1 + 2.1 # 4 converted to float
# str1 = "My int:" + int1 # Error: no implicit type conversion from int to string
int2 = 4 + True # 5: bool is implicitly converted to int
```

### Explicit type conversion


```python
str1 = "My int:" + str(int1)
v1 = int(2.7) # 2
v2 = int(-3.9) # -3
v3 = int("2") # 2
v4 = int("11", 16) # 17, base 16
v5 = long(2) # this supports only in python 2 vesion
v6 = float(2) # 2.0
v7 = float("2.7") # 2.7
v8 = float("2.7E-2") # 0.027
v9 = float(False) # 0.0
vA = float(True) # 1.0
vB = str(4.5) # "4.5"
vC = str([1, 3, 5]) # "[1, 3, 5]"
vD = bool(0) # False; bool fn since Python 2.2.1
vE = bool(3) # True
vF = bool([]) # False - empty list
vG = bool([False]) # True - non-empty list
vH = bool({}) # False - empty dict; same for empty tuple
vI = bool("") # False - empty string
vJ = bool(" ") # True - non-empty string
vK = bool(None) # False
vL = bool(len) # True
vM = set([1, 2])
vN = list(vM)
vO = list({1: "a", 2: "b"}) # dict -> list of keys
vP = tuple(vN)
vQ = list("abc") # ['a', 'b', 'c']
print v1, v2, v3, type(v1), type(v2), type(v3)
```

<span style="color:red; font-family:Comic Sans MS">References</span>  
<a href="https://www.programiz.com" target="_blank">https://www.programiz.com</a>  
https://realpython.com/python-data-types/#strings  

<span style="color:red; font-family:brandon">Further  Resources</span>  
<a href="https://realpython.com/python-variables/" target="_blank">https://realpython.com/python-variables/</a>  
<a href="https://realpython.com/python-data-types/" target="_blank">https://realpython.com/python-data-types/</a>  
<a href="https://realpython.com/python-operators-expressions/" target="_blank">https://realpython.com/python-operators-expressions/</a>  
<a href="https://realpython.com/python-strings/" target="_blank">https://realpython.com/python-strings/</a>  
  
<a href="https://www.datacamp.com/community/tutorials/data-structures-python" target="_blank">https://www.datacamp.com/community/tutorials/data-structures-python</a>  
