# python  
Apress - Begining Python - From Novice to Professional

## The Interactive Interpreter
```Shell
20160308 22:14:06 lshang@elemos:/home/lshang 
$ python
Python 2.7.3 (default, Jun 22 2015, 19:33:41) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> print "Hello, world!"
Hello, world!
>>> 
```

## Numbers and Expressions
```Python
>>> 1 + 9
10
>>> 1/2
0
>>> from __future__ import division
>>> 1/2
0.5
```
+  Large Integers  
   A long (or long integer) is written with and L at the end.  
```Python
>>> 100000000000000000000
100000000000000000000L
```
+  Hexadecimals and octals  
   The first digit in both of these is zero.  
```Python
>>> 0xAF
175
>>> 010
8
```

## Variables  
A variable is basically a name that represents (or refers to) some value.  Variable names can consist of letters, digits and underscore characters(_). A variable can't begin with a digit. 
```Python
>>> pi = 3.14
>>> r  = 1
>>> 2 * pi * r
6.28
```

## Statements  
The difference between a statement and an expression: an expression is something, while a statement does something. 
```Python
>>> pi = 3.14
>>> r  = 1
>>> 2 * pi * r
6.28
>>> print 2 * pi * r
6.28
```

## Getting Input from the User  
```Python
>>> input("x: ")
x: 0.618
0.618
>>> raw_input("x: ")
x: 0.618
'0.618'
```

## Functions  
```Python
>>> round(1.0/2.0)
1.0
>>> pow(2, 3)
8
```

## Modules  
```Python
>>> import math
>>> math.sqrt(100)
10.0
```

## Python Script/File
+ shebang
```Python
#!/usr/bin/env python
```
+ Comments
Make sure your comments say significant things and don't simply restate what is already obvious from the code. 

## Strings
+ Single-Quoted Strings and Escaping Quotes
```Python
>>> 'Hello, world!'
'Hello, world!'
>>> 'Let\'s go!'
"Let's go!"
>>> "Let's go!"
"Let's go!"
>>> '"Hello, world!" she said'
'"Hello, world!" she said'
>>> '"Hello, world!" she said'
'"Hello, world!" she said'
```
+ Concatenating Strings
```Python
>>> "Let's say " '"Hello, world!"'
'Let\'s say "Hello, world!"'
>>> "Hello, " + "world!"
'Hello, world!'
```
