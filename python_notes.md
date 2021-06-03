# Python
## [Table of content](#python)
  - [Variables](#variables)
  - [Strings](#strings)
  - [Lists](#lists)
  - [Tuples](#tuples)
  - [Dictionary](#dictionary)
  - [Set](#set)
  - [Looping through items](#looping-through-items)
  - [Control flow](#control-flow)
  - [User input](#user-input)
  - [Functions](#functions)
  - [Recursion](#recursion)
  - [Lambda functions](#lambda-functions)
  - [Filter, Map](#filter-map)
  - [Object oriented programming](#object-oriented-programming)
  - [Modules](#modules)
  - [File handling](#file-handling)
  - [Exception](#exception)
  - [Python STL](#python-stl)
  - [Storing data as JSON](#storing-data-as-json)
  - [Testing](#testing)
  - [Python style guide (PEP8)](#python-style-guide-pep8)
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Variables
* eg: `this_is_variable`
* Only letters, numbers and underscores.
* Avoid using python keywords and names.
* Use only lowercase letters
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Strings
```python
s1 = 'This is a string' # conventional usage
s2 = "This is a string"
s3 = """
    This is a multi-line string
    """

s = s1 + s3             # concatenation

string_length = len(s)  # length of string

ch = s1[2]              # h. Character access
subset_ch = s1[1:5]     # his i

repeat_str = 'abc'*5    # abcabcabcabcabc

s = " This is hello from Apurv  "   
len(s)                              # 27
s.title()                           # " This Is Hello From Apurv  "
s.upper()                           # " THIS IS HELLP FROM APURV  "
s.lower()                           # " this is hello from apurv  "
s.strip()                           # "This is hello from Apurv"
s.split()                           # ["This", "is", "hello", "from", "Apurv"]
s.split('s')                        # ["Thi", "i", "hello", "from", "Apurv"]
s.count('i')                        # Counting strings → 2
s.replace('Hello','Goodbye')        # Replacing substring
s.find('is')                        # Returns index of first found word (-1 if not present). → 6
s.swapcase()                        # ' tHIS IS HELLO FROM aPURV    '
s_reverse = s[::-1]                 # '  vrupA morf olleh si sihT '
s = 'My age is'+ str(24)            # need to convert int object to string to concatenate
'|{:<25}|'.format('left aligned'))  # |left aligned    | # character width 25
'|{:>25}|'.format('right aligned')) # |   right aligned|
'|{:^25}|'.format('centered'))      # |    centered    |

# Formatting strings using "f"
first_name = "Apurv"                
s = f"Hello! This is {first_name}"

# String evaluation
mul = "5*2"
eval(mul)   # 10
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Lists
```python
items = ['item_1', 'item_2', 456, 'item_3', 123]

list1[1]                    # access
list1[-1]                   # 1st item from back
list1[-3]                   # 3rd item from back

# slicing
list1[1:4]
list1[-3:]
item[:3]

list1_alias = list1         # create alias of the list,
                            # pointing to same memory location
list1_copy = list1[:]       # copying all elements

len(list1)                  # number of items in list

list2 = ['a','b','c']       
list1.append('a')           # list1 = ['item_1', 'item_2', 456, 'item_3', 123, 'a']
list1.extend(list2)         # list1 = ['item_1', 'item_2', 456, 'item_3', 123, 'a', 'b', 'c']
list1 += list2              # list1 = ['item_1', 'item_2', 456, 'item_3', 123, 'a', 'b', 'c']

list1.insert(2,'crazy')     # list1 = ['item_1', 'item_2', 'crazy', 456, 'item_3', 123]

list3 = list1 + list2       # concatenation 
# list3 = ['item_1', 'item_2', 456, 'item_3', 123, 'a', 'b', 'c']

popped_item = list1.pop()   # Removing element at end. Returns 123
del list1[<INDEX>]          # removing selected item
list1.remove(<ITEM>)        # removing selected item with name

list1.sort()                # sorting items in the list
list1.sort(reverse = True)  # reversing list
list1.reverse()             # reversing list

list1.count('a')            # retuns 1

# range function
num_list = list(range(10))      # [0,1,2,3,4,5,6,7,8,9]
num_list = list(range(0,10))    # [0,1,2,3,4,5,6,7,8,9]
num_list = list(range(0,10,2))  # [0,2,4,6,8]

min(num_list)   # Minimum value in the list
max(num_list)   # Maximum value in the list   
sum(num_list)   # Sum of all the values in the list
```

List comprehension

```python
# [ <expression> for item in iterable <if optional_condition> ]
#list1 = [<OPERATION ON EACH ITEM> for item in range(0,10)]
squares = [item**2 for item in range(0,10)]
cubes = [item**3 for item in num_list]
squares_even = [item**2 for item in range(0,5) if item%2==0]   # [0,4,16]
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Tuples
Lists are mutable → items can be changed
Tuples are immutable. → items can't be changed once defined

```python
tuple_items = (20,60,'a',"this is item",'a',Student('apurv', 'Kulkarni'))
tuple_one = (100,)      # tuple with one element
tuple_items[<INDEX>]    # access
tuple_items[0] = 100    # Error. Immutable.
tuple_items.count('a')  # returns 2
tuple_items.count('60') # returns 1
len(tuple_items)        # returns 6

tup1,tup2 = (1,'a',2,'b'),(3,'c',4,'d')
tup3 = (5,tup1,45,tup2,'f') # nested tuples

```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Dictionary
```python
# general method
students = {
    'First_name':'Apurv',
    'Last_name':'Kulkarni',
    'Age':27
    }
# keys not as string
students = dict(First_name='Apurv', Last_name='Kulkarni', Age=27)
# key-value pair as tuples
students = dict([('First_name','Apurv'), ('Last_name','Kulkarni'), ('Age',27)])
# key-value pair as list
students = dict((['First_name','Apurv'], ['Last_name','Kulkarni'], ['Age',27]))

students['First_name']   # Access values
students.get('Subjects') # Access values
students.get('Subjects','No keys exist') # returns 2nd argument if value doesn't exist 

students.keys()          # get all the list of keys
students.values()        # get all the values
students.items()         # get all the keys and values
students.pop('Age')      # remove all the value of the key
                         # and return the corresponding value
del students['Age']      # removing key,value from dictionary

print('Degree' in students) # check membership of a key

# adding new values to the existing dictionary
students.update({
    'Subjects': ['FEM', 'CFD', 'MBS'],
    'Marks':[1,2,3,4]
    })
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Set
* Unordered (unindexed) collection.
* Are immutable.
* Formed when curly brackets are used without key,value pairs.
* It always contains unique values.
* `set()`: Forms list of unique items from list
```python
my_set = {1,2,3,'a'}
my_set = {1,1,2,2,'a','a'}  # {1,2,'a'}

dup_list = [1,2,3,4,1,'a',1,1,2,'b',1,8,'b',"This"]
unique_set = set(dup_list)  # {1, 2, 3, 4, 8, 'a', 'b', 'This'}

unique_set.add('apple')                 # {1, 2, 3, 4, 8, 'a', 'b', 'This', 'apple'}
unique_set.update(['apple', 'banana'])  # {1, 2, 3, 4, 8, 'a', 'b', 'This', 'apple', 'banana'}
unique_set.remove('This')               # {1, 2, 3, 4, 8, 'a', 'b'}
unique_set.discard('This')              # {1, 2, 3, 4, 8, 'a', 'b'}

set1 = {1, 2, 3, 4, 5, 9}
set2 = {3, 4, 5, 6, 7, 8}
set3 = set1 | set2      # Union: {1, 2, 3, 4, 5, 6, 7, 8, 9}
set3 = set1 & set2      # Intersection: {3, 4, 5}
set3 = set1 - set2      # Difference: {1, 2, 9}
set3 = set1 ^ set2      # Symmetric Difference: {1, 2, 6, 7, 8, 9}
```

| Method                        | Description                                                                    |
| ----------------------------- | ------------------------------------------------------------------------------ |
| add()                         | Adds an element to the set                                                     |
| clear()                       | Removes all the elements from the set                                          |
| copy()                        | Returns a copy of the set                                                      |
| difference()                  | Returns a set containing the difference between two or more sets               |
| difference_update()           | Removes the items in this set that are also included in another, specified set |
| discard()                     | Remove the specified item                                                      |
| intersection()                | Returns a set, that is the intersection of two other sets                      |
| intersection_update()         | Removes the items in this set that are not present in other,specified set(s)   |
| isdisjoint()                  | Returns whether two sets have a intersection or not                            |
| issubset()                    | Returns whether another set contains this set or not                           |
| issuperset()                  | Returns whether this set contains another set or not                           |
| pop()                         | Removes an element from the set                                                |
| remove()                      | Removes the specified element                                                  |
| symmetric_difference()        | Returns a set with the symmetric differences of two sets                       |
| symmetric_difference_update() | inserts the symmetric differences from this set and another                    |
| union()                       | Return a set containing the union of sets                                      |
| update()                      | Update the set with the union of this set and others                           |

------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->

## Looping through items
```python
# method 1
for item in items:
    print(item)

# method 2
for i in range(0,15):
    print(items[i])

# looping through dictionary
for key,value in students.items():
    <STATEMENT>

for key in students.keys():
    "do something with students['key']"

for key in students:
    "do something with students['key']"

```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Control flow
conditions
```python
<, >, ==, <=, >=    # comparison operators
and, or             # for combining more than one conditions
item in item_list   # return true/false
```

if-else
```python
if <CONDITION>:
    <STATEMENT>
elif <CONDITION>:
    <STATEMENT>
else:
    <STATEMENT>
```

while
```python
while <CONDITION>:
    <STATEMENT>

my_list = ['a','e']
while my_list:      # runs the loop until the list is empty
    <STATEMENTS>
```

break,continue, pass
```python
for <CONDITION>:
    <STATEMENT1>
    if <CONDITION>:
        continue    # skips the <Statement2> and returns to beginning of the loop
    <STATEMENT2>

for <CONDITION>:    # same as "continue"
    pass            

for <CONDITION>:
    <STATEMENT1>
    break           # exits loop at this point
    <STATEMENT2>
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## User input 
`input()`: Pauses program and takes user input in the string format
```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Functions
```python
def my_function(arg1,arg2,arg3="default value"):
    <Statements>
    return <Something or 0>

my_function("Apurv","Kulkarni")
my_function("Apurv","Kulkarni",45)
my_function(arg1="Apurv",arg2="Kulkarni")
my_function(arg1="Apurv","Kulkarni") # error
my_function("Apurv",arg2="Kulkarni")
someting = my_function("Apurv",arg2="Kulkarni")

# for arbitrary number of arguments
def my_function(*arg):      # arg is the list of values
    first_value = arg[0]
    second_value = arg[1]
    .
    .
    return <Something or 0>

# arbitrary argument with positional argument.
# Generally known as - *args
def my_pizza(size, *toppings):
    <Statements>
    return <Something or 0>

# passing arbitrary dictionary to the function
# Generally known as - **kwargs
def build_profile(first, last, **user_info):
    user_info['name'] = f"{first.title()} {last.title()}"
    print(user_info['name'])
    for keys,values in user_info.items():
        print(f'{keys.title()} - {values}')    
    return user_info

# output with dictionary of all the values
my_man = build_profile("Apurv","Kulkarni",location="Dresden",degree="MSc CMS")
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Recursion
```python
def recursive_function(arg_1):
    if arg_1 == 0:                  # Base case
        return <SOMETHING>
    else:
        recursive_function(arg_1-1) # Recursive call
```
* More expensive than iteration
  * Function call is expensive as it requires setting up of stack for each function call
  * Requires unwinding of stack on function return
* *Tail recursion* → An optimized recursion
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Lambda functions
```python
func = lambda x: x**3
print(func(4))          # 64

num_list = [1,2,3,4,5,6,7,8,9]
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Filter, Map
```python
# Filter: filter(<function>,<iterable>)
# Use case with lambda function
is_even = lambda x: x%2 == 0
num_list1 = list(filter(is_even,num_list))  # [2, 4, 6, 8]

# Use case with a function
def is_odd(x):
    return (x%2 != 0)
num_list2 = list(filter(is_odd,num_list))   # [1, 3, 5, 7, 9]

# Use case with class
class Employee():    
    def __init__(self,name,age):
        self.name_ = name.title()
        self.age_ = age

    def __str__(self):              # for printing statements
        return f'Employee({self.name_},{self.age_})'

elist = [Employee('Apurv kulkarni',27),
         Employee('Apurv2 kulkarni2',12), 
         Employee('Apurv3 kulkarni3',20)]

age_22 = list(filter(lambda x: x.age_<=22,elist))   # [Employee('Apurv2 kulkarni2',12), Employee('Apurv3 kulkarni3',20)]

# Map: map(<function>,<iterable>)
square = lambda x: x**2
num_list3 = list(map(square,num_list))      # [1, 4, 9, 16, 25, 36, 49, 64, 81]
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Object oriented programming
* Classes
    ```python
    class Dog:
        """ Dog class"""

        def __init__(self, name, age=0):  # default method to set attributes
            """Initialize name and age attributes."""
            self.name_ = name
            self.age_ = age
            self.owner_ = "Apurv"  # default attribute value
        
        def bark(self):
            print("Bho! Bho! Bho!")

        def sit(self):          # Method
            """Simulate a dog sitting"""
            print(f"{self.name_} is sitting.")

        def update_age(self, age):          # Method
            self.age_ = age
        
        my_dog = Dog("appu",1)  # Creating an instance
        my_dog.age              # Accessing attributes
        my_dog.sit()            # Calling methods
        my_dog.age = 2          # modifying attribute values
        my_dog.update_age(4)    # modyfying attribute via method
    ```
    * Method: Function that is a prt of the class
        * `__init__(self, arg1, arg2,..)` : Called on creating new instance. `self` must be provided as first argument. It is automatically passed to other methods in class.  
        * Variable access inside method: `self.arg1`
    * Accessing attributes: `my_dog.age`
  
* Inheritance
    ```python
    class Labrador(Dog):                # Subclass of superclass Dog

        def __init__(self, name, age):
            super().__init__(name, age) # Initializing attributes using super()
            self.color_ = golden        # Additional attribute

        def sit(self):                  # Method override
            print("Stare and Wag tail!")

        def roll_over(self):            # Method override    
            super().roll_over()          # Use super calss method
            print("Stare and Wag tail!") # Add some functionality

    my_lab = Labrador("AJ",2)
    my_lab.bark()                       # Inherited method
    my_lab.color_                       # Additional attribute
    my_lab.sit()                        # Overridden method
    ```
* Just like functions, classes can also be stored in another file and can be imported
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Modules
```python
import module_name
function_name()

import module_name as mp
mp.function_name()

from module_name import function_name
function_name()

from module_name import function_name as fn
fn()

from module_name import * # not recommended
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## File handling
```python
with open(<filename>,<mode>) as f:
    <Do_something_with_file>

with open(<filename>,'r') as f:
    contents = f.read()     # saves the content as a string

    for line in f:          # read line by line when in 
        print(line)

with open(<filename>,'w') as f:     # writing to a file
    f.write("Writing new content.")

with open(<filename>,'a') as f:     # appending to a file
    f.write("Adding new content.")
```

| Mode | Description                                   |
| ---- | --------------------------------------------- |
| `r`  | read file only                                |
| `r+` | read and write                                |
| `w`  | write file. Writes new file if doesn't exists |
| `w+` | overwrites the files and its contents         |
| `a`  | appends contents                              |

------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Exception
```python
    try:                        # Try statement that needs to be tested
        <Statements>
    except ZeroDivisionError:   # Except with some predefined exceptions
        <Statements>
    except:                     # Exception handlining in general way
        <Statements>
    else:                       # Runs the code block after try block is completed 
        <Statements>
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Python STL
```python
from random import randint
randint(<Start_num>,<End_num>)

from random import choice
players = ['a','b','c']
random_selection = choice(players)  # randomly selects on item
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Storing data as JSON
* JSON: JavaScript Object Notation
```python
import json
num_list = [1,2,44,56,81,5]

filename='numbers.json'
with open(filename,'w') as f:   # saving file
    json.dump(num_list,f)

with open(filename) as f:       # loading file
    numbers = json.load(f)
```
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Testing
* Unit tests: Tests to check one specific aspect of the code
* Test case: A collection of unit tests. A good test case considers all kind of inputs to a function/code.

* Testing a function
    ```python
    import unittest
    def get_formatted_name(first, last, middle=''):
        if first == '' or last == '':
            first = input("Enter firstname: ")
            last = input("Enter lastname: ")
        if middle != '':
            middle = ' ' + middle
        last = ' ' + last
        return first.title() + middle.title() + last.title()

    # Class contaning series of unit tests
    # It is inherited from unittest.TasteCase
    class NameTestCase(unittest.TestCase):
        """Test for function get_formatted_name"""

        # Unit test. Name should have prefix 'test_'
        def test_first_last_name(self):
            """To check if providing only first name and last name works"""
            formatted_name = get_formatted_name('apurv', 'kulkarni')
            self.assertEqual(formatted_name, 'Apurv Kulkarni')

        def test_first_last_middle_name(self):
            """To check if providing only first name and last name works"""
            formatted_name = get_formatted_name('apurv', 'kulkarni', 'deepak')
            self.assertEqual(formatted_name, 'Apurv Deepak Kulkarni')

    if __name__ == '__main__':      # running all tests in the file
        unittest.main()
    ```

* Testing a class
  * Testing a method  

* Assert methods in `unittest`:
  | Method                    | Use                                 |
  | ------------------------- | ----------------------------------- |
  | `assertEqual(a, b)`       | Verify that `a == b`                |
  | `assertNotEqual(a, b)`    | Verify that `a != b`                |
  | `assertTrue(x)`           | Verify that `x` is True             |
  | `assertFalse(x)`          | Verify that `x` is False            |
  | `assertIn(item, list)`    | Verify that `item` is in `list`     |
  | `assertNotIn(item, list)` | Verify that `item` is not in `list` |
------------------
<!-- ====================================================================== -->
<!-- ====================================================================== -->
## Python style guide (PEP8)
* 4 spaces fro indentation
* Line length 
  * Everything <= 79 characters
  * Comments <= 72 charachters
* Naming
    * Functions:
      * Function name
        * lowercase with underscores as seperator. 
              `my_function`, `build_profile`
      * Arguments
        * lowercase with underscores as seperator. 
              `arg_1`, `arg_2`
        * no spaces on either side of assignment operator.
              `def my_function(arg_1, arg_2, arg_3="default value")`
      * Passing arguments: No spaces on either side of assignment operator.
          `my_function(arg_1=val1, arg_2="val2")`
      * Comments: Immidiately after function definition in docstring
          `""" Function description """`
    * Class
      * Class name: `CamelCase`. Eg: `ElectricVehicle`, `UniversityStudent`