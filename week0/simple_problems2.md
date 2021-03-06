## Problem 23 - Count words

Given a list of strings, implement a function, called ```count_words(arr)``` which returns a dictionary of the following kind:

```python
{ "word" : count }
```

Where ```count``` is the count of occurrences of the __word__ in the list ```arr```.


### Signature

```python
def count_words(arr):
    # Implementation
```

### Test examples

```
>>> count_words(["apple", "banana", "apple", "pie"])
{'apple': 2, 'pie': 1, 'banana': 1}
>>> count_words(["python", "python", "python", "ruby"])
{'ruby': 1, 'python': 3}
```

## Problem 24 - Unique words

Implement a function, called ```unique_words_count(arr)``` which returns the number of different words in ```arr```.

```arr``` is a list of strings.

### Signature

```python
def unique_words_count(arr):
    # Implementation
```

### Test examples

```
>>> unique_words_count(["apple", "banana", "apple", "pie"])
3
>>> unique_words_count(["python", "python", "python", "ruby"])
2
>>> unique_words_count(["HELLO!"] * 10)
1
```

## Problem 25 - Group By
This problem is from the [Python 2013 course in FMI](http://2013.fmi.py-bg.net/)
You can see the original problem statement here - http://2013.fmi.py-bg.net/tasks/2

Implement a function, called ```groupby(func, seq)``` which returns a dictionary, which keys are determined by the ```func``` argument.

The values are items from ```seq```

### Signature

```python
def groupby(func, seq):
    # Implementation
```

### Test examples

```
>>> groupby(lambda x: x % 2, [0,1,2,3,4,5,6,7])
{0: [0, 2, 4, 6], 1: [1, 3, 5, 7]}
>>> groupby(lambda x: 'odd' if x % 2 else 'even', [1, 2, 3, 5, 8, 9, 10, 12])
{'even': [2, 8, 10, 12], 'odd': [1, 3, 5, 9]}
>>> groupby(lambda x: x % 3, [0, 1, 2, 3, 4, 5, 6, 7])
{0: [0, 3, 6], 1: [1, 4, 7], 2: [2, 5]}
```

## Problem 26 - Spam and Eggs
This is a problem from the [Python 2012 course in FMI](http://2012.fmi.py-bg.net/)

You can see the original problem statement here - http://2012.fmi.py-bg.net/tasks/1

Implement a function, called ```prepare_meal(number)``` which takes an integer and returns a string, generated by the following algorithm:

__Еggs:__

If there is an integer ```n```, such that ```3^n``` divides ```number``` and ```n``` is the largest possible, the result should be a string, containing ```n``` times ```spam```

For example:

```
>>> prepare_meal(3)
'spam'
>>> prepare_meal(27)
'spam spam spam'
>>> prepare_meal(7)
''
```

__Spam:__

If number is divisible by 5, add ```and eggs``` to the result.

For example:

```
>>> prepare_meal(5)
'eggs'
>>> prepare_meal(15)
'spam and eggs'
>>> prepare_meal(45)
'spam spam and eggs'
```

__Notice that in the first case, there is no "and". In the rest - there is.__

### Signature

```python
def prepare_meal(number):
    # Implementation
```

### Test examples

```
>>> prepare_meal(5)
"eggs"
>>> prepare_meal(3)
"spam"
>>> prepare_meal(27)
"spam spam spam"
>>> prepare_meal(15)
"spam and eggs"
>>> prepare_meal(45)
"spam spam and eggs"
>>> prepare_meal(7)
""
```

## Problem 27 - Reduce file path

A file path in a Unix OS looks like this - ```/home/radorado/code/hackbulgaria/week0```

We start from the root - ```/``` and we navigate to the destination fodler.

But there is a problem - if we have ```..``` and ```.``` in our file path, it's not clear where we are going to end up.

* ```..``` means to go back one directory
* ```.```  means to stay in the same directory
* we can have more then one ```/``` between the directories - ```/home//code```

So for example : ```/home//radorado/code/./hackbulgaria/week0/../``` reduces to ```/home/radorado/code/hackbulgaria```


Implement a function, called ```reduce_file_path(path)``` which takes a string and returns the reduced version of the path.

* Every ```..``` means that we have to go one directory back
* Every ```.``` means that we are staying in the same directory
* Every extra ```/``` is unnecessary
* Always remove the last ```/```

### Signature

```python
def reduce_file_path(path):
    # Implementation
```

### Test examples
```
>>> reduce_file_path("/")
"/"
>>> reduce_file_path("/srv/../")
"/"
>>> reduce_file_path("/srv/www/htdocs/wtf/")
"/srv/www/htdocs/wtf"
>>> reduce_file_path("/srv/www/htdocs/wtf")
"/srv/www/htdocs/wtf"
>>> reduce_file_path("/srv/./././././")
"/srv"
>>> reduce_file_path("/etc//wtf/")
"/etc/wtf"
>>> reduce_file_path("/etc/../etc/../etc/../")
"/"
>>> reduce_file_path("//////////////")
"/"
>>> reduce_file_path("/../")
"/"
```

## Problem 28 - Word from a^nb^n

Implement a function, called ```is_an_bn(word)``` that checks if the given ```word``` is from the ```a^nb^n for n>=0``` language. Here, ```a^n``` means a to the power of n - __repeat the character "a" n times.__

Lets see few words from this language:

* for ```n = 0```, this is the empty word ```""```
* for ```n = 1```, this is the word ```"ab"```
* for ```n = 2```, this is the word ```"aabb"```
* for ```n = 3```, this is the word ```"aaabbb"```
* and so on - first, you repeat the character "a" n times, and after this - repeat "b" n times

The function should return True if the given ```word``` is from ```a^nb^n for n>=0" for some n.

### Signature

```python
def is_an_bn(word):
    # Implementation
```

### Test examples

```
>>> is_an_bn("")
True
>>> is_an_bn("rado")
False
>>> is_an_bn("aaabb")
False
>>> is_an_bn("aaabbb")
True
>>> is_an_bn("aabbaabb")
False
>>> is_an_bn("bbbaaa")
False
>>> is_an_bn("aaaaabbbbb")
True
```
## Problem 29 - Simplify fractions

Implement a function, called ```simplify_fraction(fraction)``` that takes a tuple of the form ```(nominator, denominator)``` and simplifies the fraction.

The function should return the fraction in it's irreducible form.

For example, a fraction ```3/9``` can be reduced by dividing both the nominator and the denominator by 3. We end up with ```1/3``` which is irreducible.

### Signature

```python
def simplify_fraction(fraction):
    # Implementation
```

### Test examples

```
>>> simplify_fraction((3,9))
(1,3)
>>> simplify_fraction((1,7))
(1,7)
>>> simplify_fraction((4,10))
(2,5)
>>> simplify_fraction((63,462))
(3,22)
```

## Problem 30 - Sort array of fractions

Implement a function, called ```sort_fractions(fractions)``` where ```fractions``` is a list of tuples of the form ```(nominator, denominator)```.

Both the nominator and the denominator are integers.

The function should return the list, sorted in increasing order.

### Signature

```python
def sort_fractions(fractions):
    # Implementation
```

### Test examples

```
>>> sort_fractions([(2, 3), (1, 2)])
[(1, 2), (2, 3)]
>>> sort_fractions([(2, 3), (1, 2), (1, 3)])
[(1, 3), (1, 2), (2, 3)]
>>> sort_fractions([(5, 6), (22, 78), (22, 7), (7, 8), (9, 6), (15, 32)])
[(22, 78), (15, 32), (5, 6), (7, 8), (9, 6), (22, 7)]
```

## Problem 31 - Fibonacci lists

Implement a function, called ```nth_fib_lists(listA, listB, n)``` which takes two list of integers as ```listA``` and ```listB``` and returns the n-th member of the fibonacci sequence, that is created by the following algorithm:

* for n = 1, it's listA
* for n = 2, it's listB
* for n = 3, it's listA + listB where + is list concatenation
* and so on, just like a fibonacci

### Signature

```python
def nth_fib_lists(listA, listB, n)
```

### Test examples

```
>>> nth_fib_lists([1], [2], 1)
[1]
>>> nth_fib_lists([1], [2], 2)
[2]
>>> nth_fib_lists([1, 2], [1, 3], 3)
[1, 2, 1, 3]
>>> nth_fib_lists([], [1, 2, 3], 4)
[1, 2, 3, 1, 2, 3]
>>> nth_fib_lists([], [], 100)
[]
```

## Problem 31.5 - Is member of nth fibonacci lists

Implement a function, called ```member_of_nth_fib_lists(listA, listB, needle)``` which checks if ```needle``` is a part of the fibonacci sequence, created by ```listA``` and ```listB``` for the first two elements.

### Signature

```python
def member_of_nth_fib_lists(listA, listB, needle):
    # Implement
```

### Test examples

```
>>> member_of_nth_fib_lists([1, 2], [3, 4], [5, 6])
False
>>> member_of_nth_fib_lists([1, 2], [3, 4], [1,2,3,4,3,4,1,2,3,4])
True
>>> member_of_nth_fib_lists([7,11], [2], [7,11,2,2,7,11,2])
True
>>> member_of_nth_fib_lists([7,11], [2], [11,7,2,2,7])
False
```

## Problem 32 - Goldbach Conjecture

Implement a function, called ```goldbach(n)``` which returns a list of tupples, that is the goldbach conjecture for the given number ```n```

The Goldbach Conjecture states:

> Every even integer greater than 2 can be expressed as the sum of two primes.

Keep in mind that there can be more than one combination of two primes, that sums up to the given number.

__The result should be sorted by the first item in the tuple.__

For example:

* ```4 = 2 + 2```
* ```6 = 3 + 3```
* ```8 = 3 + 5```
* ```10 = 3 + 7 = 5 + 5```
* ```100 = 3 + 97 = 11 + 89 = 17 + 83 = 29 + 71 = 41 + 59 = 47 + 53```

### Signature

```python
def goldbach(n):
    # Implementation
```

### Test examples

```
>>> goldbach(4)
[(2,2)]
>>> goldbach(6)
[(3,3)]
>>> goldbach(8)
[(3,5)]
>>> goldbach(10)
[(3,7), (5,5)]
>>> goldbach(100)
[(3, 97), (11, 89), (17, 83), (29, 71), (41, 59), (47, 53)]
```

## Problem 33 - Magic Square

Implement a function, called ```magic_square(matrix)``` that checks if the given array of arrays ```matrix``` is a magic square.

A magic square is a square matrix, where the numbers in each row, and in each column, and the numbers in the forward and backward main diagonals, all add up to the same number.

### Signature

```python
def magic_square(matrix):
    # Implementation
```
### Test examples

```
>>> magic_square([[1,2,3], [4,5,6], [7,8,9]])
False
>>> magic_square([[4,9,2], [3,5,7], [8,1,6]])
True
>>> magic_square([[7,12,1,14], [2,13,8,11], [16,3,10,5], [9,6,15,4]])
True
>>> magic_square([[23, 28, 21], [22, 24, 26], [27, 20, 25]])
True
>>> magic_square([[16, 23, 17], [78, 32, 21], [17, 16, 15]])
False
```

## Problem 34 - Is sudoku solved?

Implement a function, called ```sudoku_solved(sudoku)```, that checks if the given ```sudoku``` matrix is solved correctly.

```sudoku``` is a 9x9 matrix of integers.

A sudoku is solved correctly, if:

* Each row contains the numbers from 1 do 9 without repeating a number
* Each column contains the numbers from 1 to 9, without repeating a number
* All 3x3 subgrids contains the numbers from 1 to 9, without repeating a number

For better reference, check Wikipedia - http://en.wikipedia.org/wiki/Sudoku

### Signature

```python
def sudoku_solved(sudoku):
    # Implementation
```

### Test examples

```
>>> sudoku_solved([
[4, 5, 2, 3, 8, 9, 7, 1, 6],
[3, 8, 7, 4, 6, 1, 2, 9, 5],
[6, 1, 9, 2, 5, 7, 3, 4 ,8],
[9, 3, 5, 1, 2, 6, 8, 7, 4],
[7, 6, 4, 9, 3, 8, 5, 2, 1],
[1, 2, 8, 5, 7, 4, 6, 3, 9],
[5, 7, 1, 8, 9, 2, 4, 6, 3],
[8, 9, 6, 7, 4, 3, 1, 5 ,2],
[2, 4, 3, 6, 1, 5, 9, 8, 7]
])
True
>>> sudoku_solved([
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9],
[1, 2, 3, 4, 5, 6, 7, 8, 9]
])
False
```

---


## Bonus Round 1 - Division by zero

Check this TopCoder problem - http://community.topcoder.com/stat?c=problem_statement&pm=12911&rd=15843

Implement a Python program, that solves it.

Here is a piece of code with unit tests, to cover the problem statement cases. It assumes that your file name is ```division_by_zero.py```.


```python
# filename - division_by_zero_tests.py
from division_by_zero import count_numbers
import unittest


class CountNumbersTest(unittest.TestCase):
    """Testing the 250 problem from TopCoder SRM 610 Round 1 Div 2"""
    def test_cases_from_problemt_statement(self):
        self.assertEqual(count_numbers([9, 2]), 3)
        self.assertEqual(count_numbers([8, 2]), 3)
        self.assertEqual(count_numbers([50]), 1)
        self.assertEqual(count_numbers([1, 5, 8, 30, 15, 4]), 11)
        self.assertEqual(count_numbers([1, 2, 4, 8, 16, 32, 64]), 7)
        self.assertEqual(count_numbers([6, 2, 18]), 7)

if __name__ == '__main__':
    unittest.main()

```

To run the tests, simply type ```python division_by_zero_tests.py``` in your console.

## Bonus Round 2 - Magic String

Check this TopCoder problem - http://community.topcoder.com/stat?c=problem_statement&pm=13004&rd=15842

Implement a Python program, that solves it.

Here is a piece of code with unit tests, to cover the problem statement cases. It assumes that your file name is ```magic_string.py```.

```python
from magic_string import magic_string
import unittest


class MagicStringTest(unittest.TestCase):
    """Testing magic_string - 250 problem from TC SRM 609 Div 2"""
    def test_problem_statement_cases(self):
        self.assertEqual(2, magic_string(">><<><"))
        self.assertEqual(0, magic_string(">>>><<<<"))
        self.assertEqual(4, magic_string("<<>>"))
        self.assertEqual(20,
                         magic_string(
                         "<><<<>>>>><<>>>>><>><<<>><><><><<><<<<<><<>>><><><"))

if __name__ == '__main__':
    unittest.main()

```

## Bonus Round 3 - One Dimensional Robot

Check this TopCoder problem - http://community.topcoder.com/stat?c=problem_statement&pm=13000&rd=15841

Implement a Python program, that solves it.

Here is a piece of code with unit tests, to cover the problem statement cases. It assumes that your file name is ```oned_robot.py```.

```python
from oned_robot import final_position
import unittest


class OneDimensionalRobotTests(unittest.TestCase):
    """Testing the 250 problem from TC 608 SRM Div 250"""

    def test_final_position_problem_statement_cases(self):
        self.assertEqual(2, final_position("RRLRRLLR", 10, 10))
        self.assertEqual(4, final_position("RRRRR", 3, 4))
        self.assertEqual(-1, final_position("LLLLLLLLLLR", 2, 6))
        self.assertEqual(20, final_position(
            "RRRRRRRLRRLRRRRRRRRRRRRLRLRRRRRRRRLRRRRRLRRRRRRRRR", 5, 20))
        self.assertEqual(-30, final_position("RLRLLLLLLLRLLLRLLLLLLLLRLLLLLRLLLRRLLLLLRLLLLLRLLL", 34, 15))

if __name__ == '__main__':
    unittest.main()
```
