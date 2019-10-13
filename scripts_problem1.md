
# ADM Homework 1 Part 1

## Hello, World!
Output: Hello, World!


```python
print("Hello, World!")
```

## Python If-Else
Task:
Given an integer, n, perform the following conditional actions:
If n is odd, print Weird
If n is even and in the inclusive range of 2 to 5, print Not Weird
If n is even and in the inclusive range of 6 to 20, print Weird
If n is even and greater than 20, print Not Weird

Input Format:
A single line containing a positive integer, n.

Constraints:
1<=n<=100

Output Format:
Print Weird if the number is weird; otherwise, print Not Weird.


```python
#!/bin/python

import math
import os
import random
import re
import sys



n = input()
n = int(n)

if n >= 1 and n <= 100:
    if n % 2 == 1 or ( n >= 6 and n <= 20 ):
        print('Weird')
    else:
        print ("Not Weird")
```

    25
    Weird
    

## Arithmetic Operator
Inputs: integers a, b.
Outputs: values of a+b, a-b, ab.


```python
if __name__ == '__main__':
    a = int(raw_input())
    b = int(raw_input())

if (a > 0 and b > 0 and a <= 10**10 and b <= 10**10):
    print(a + b)
    print(a - b)
    print(a * b)
```

## Python Division


```python
from __future__ import division

if __name__ == '__main__':
    a = int(raw_input())
    b = int(raw_input())

print(a//b)
print(a/b)
```

## Loops


```python
if __name__ == '__main__':
    n = int(raw_input())

if n>0 and n<21:
    for i in range(0,n):
        print(i**2)
```

## Write a function


```python
def is_leap(year):
    if year < 1900 or year > 10**5:
        return
    
    leap = False
    
    # Write your logic here
    if year % 4 == 0:
        leap = True
        if year % 400 and year % 100 == 0:
            leap = False
    
    return leap
```

## Print function


```python
from __future__ import print_function

if __name__ == '__main__':
    n = int(raw_input())

for i in range(1,n+1):
    print(i,end = '')
```

## List Comprehension


```python
from __future__ import print_function

# the commented part is alternative
# I wrote the other one after noticing that the problem had also the suggestion to use nested lists

#def myprint( abc ):
#    print( abc, end = '' )
#    return

#def finished( i, j, k, x, y, z, n ):
#    # indicates whether the last list of coordinates has been reached
#    sum = x+y+z
#    if n != sum:
#        if i==x and j==y and k==z:
#            return True
#        else:
#            return False
#    else:
#        if z:
#            if i==x and j==y and k==z-1:
#                return True
#            else:
#                return False
#        elif y:
#            if i==x and j==y-1:
#                return True
#            else:
#                return False
#        elif x:
#            if i==x-1:
#                return True
#            else:
#                return False
#        else:
#            return True
#    return

if __name__ == '__main__':
    x = int(raw_input())
    y = int(raw_input())
    z = int(raw_input())
    n = int(raw_input())

#myprint('[')

#if x==0 and y==0 and z==0 and n==0:
#    print( ']' )

ar = []

for i in range(x+1):
    for j in range(y+1):
        for k in range(z+1):
            if i+j+k != n:
                ar += [[i,j,k]]

print(ar)
```

## Find the Runner-Up Score


```python
if __name__ == '__main__':
    n = int(raw_input())
    arr = map(int, raw_input().split())

bool = True

if n<2 and n>10:
    bool = False
for i in arr:
    if i<-100 or i>100:
        bool = False

if bool:
    fst = -100
    rup = -100
    for i in range(n):
        if arr[i] > fst:
            rup = fst
            fst = arr[i]
        else:
            if arr[i] != fst and arr[i] > rup:
                rup = arr[i]
    print(rup)
```

## Nested Lists


```python
def minidx( l, n ):
    idx = 0
    for i in range(1,n):
        if l[i] < l[idx]:
            idx = i
    return idx

def idxNextToPrint(name, score, idxs, lenght):
    flag = 0 # flag=1 means the first printable element is found
    NTP = -1 # index of an index in idxs
    for i in range(count):
        if idxs[i] != 0:
            if flag == 0:
                flag = 1
                NTP = i
            else:
                if name[idxs[i]] < name[idxs[NTP]]:
                    NTP = i
    return NTP


name = []
score = []

n = int(raw_input())

for _ in range(n):
    name += [raw_input()]
    score += [float(raw_input())]

#pystud = []
#for i in range(n):
#    pystud += [ [ name[i], score[i] ] ]

if n>1 and n<6:
    idx1 = minidx(score, n)
    idx2 = -1
    flag = 0 # flag=1 indicates that idx2 is set as a non-negative index 
    for i in range(n):
        if score[i] != score[idx1]:
            if flag == 0:
                flag = 1
                idx2 = i
            elif score[i] < score[idx2]:
                idx2 = i
    if idx1 != idx2: # there are at least two different grades
        idxs = []
        count = 0
        # collecting idxs of the names to print
        for i in range(n):
            if score[i] == score[idx2]:
                idxs += [i]
                count += 1
        for i in range(count):
            NTP = idxNextToPrint(name, score, idxs, count)
            print(name[idxs[NTP]])
            idxs[NTP] = 0
```

## Finding the percentage


```python
def average(numbers):
    count = 0
    sum = 0
    for i in numbers:
        count += 1
        sum += i
    return sum/count

if __name__ == '__main__':
    n = int(raw_input())
    student_marks = {}
    bool = 1
    for _ in range(n):
        line = raw_input().split()
        name, scores = line[0], line[1:]
        scores = map(float, scores)
        for mark in scores:
                if mark < 0 or mark > 100:
                    bool = 0
        student_marks[name] = scores
    query_name = raw_input()

if n>1 and n<11 and bool:
    print(format(average(student_marks[query_name]),'.2f'))
```

## Lists


```python
if __name__ == '__main__':
    N = int(raw_input())
    commands = []
    ins = []
    for _ in range(N):
        line = raw_input().split()
        cmd, cmd_inputs = line[0], line[1:]
        cmd_inputs = map(int, cmd_inputs)
        commands += [cmd]
        ins += [cmd_inputs]
#print(commands)
#print(ins)
l=[]
for i in range(N):
    cmd = commands[i]
    if cmd == 'insert':
        l.insert(ins[i][0],ins[i][1])
    if cmd == 'print':
        print(l)
    if cmd == 'remove':
        l.remove(ins[i][0])
    if cmd == 'append':
        l.append(ins[i][0])
    if cmd == 'sort':
        l.sort()
    if cmd == 'pop':
        l.pop()
    if cmd == 'reverse':
        l.reverse()
```

## Tuples


```python
if __name__ == '__main__':
    n = int(raw_input())
    integer_list = map(int, raw_input().split())

    t = tuple(integer_list)
    print(hash(t))
```

## What's Your Name?


```python
def print_full_name(a, b):
    if len(a)<11 and len(b)<11:
        print ('Hello ' + a + ' ' + b +'! You just delved into python.')
```

## sWAP cASE


```python
# I don'y know if it works for every character encoding

def swap_case(s):
    length = len(s)
    news = []
    if length>0 and length<=1000:
        for i in range(length):
            order = ord( s[i] )
            ordA = ord('A')
            orda = ord('a')
            ordZ = ord('Z')
            ordz = ord('z')
            if order >= ordA and order <= ordZ:
                news += [chr(order+orda-ordA)]
            elif order >= orda and order <= ordz:
                news += [chr(order+ordA-orda)]
            else:
                news += [s[i]]
        return ''.join(news)
        # I found the join function online, trying to convert a list to a string
    else:
        return
```

## String Split and Join


```python
def split_and_join(line):
    # write your code here
    line = line.split(' ')
    return '-'.join(line)
```

## Python Mutations


```python
def mutate_string(string, position, character):
    string = list(string)
    string[position] = character
    return ''.join(string)
```

## String Validators


```python
def filtered(string):
    s_list = list(string)
    s_upper = []
    s_lower = []
    s_digit = []
    s_alnum = [ s_upper, s_lower, s_digit]
    for i in range(l):
        if s_list[i].isupper():
            s_alnum[0] += s_list[i]
        elif s_list[i].islower():
            s_alnum[1] += s_list[i]
        elif s_list[i].isdigit():
            s_alnum[2] += s_list[i]
    for i in range(3):
        s_alnum[i] = ''.join(s_alnum[i])
    return s_alnum

if __name__ == '__main__':
    s = input()
    l = len(s)
    ans = [False,False,False,False,False]
    if l>0 and l<1000:
        x = filtered(s)
        if x != ['', '', '']:
            ans[0] = True
            if x[2] != '':
                ans[2] = True
            if x[0] != '':
                ans[1] = True
                ans[4] = True
            if x[1] != '':
                ans[1] = True
                ans[3] = True
    for i in range(5):
        print(ans[i])
```

## Text Alignment


```python
#Replace all ______ with rjust, ljust or center. 

thickness = int(input()) #This must be an odd number
c = 'H'

#Top Cone
for i in range(thickness):
    print((c*i).rjust(thickness-1)+c+(c*i).ljust(thickness-1))

#Top Pillars
for i in range(thickness+1):
    print((c*thickness).center(thickness*2)+(c*thickness).center(thickness*6))

#Middle Belt
for i in range((thickness+1)//2):
    print((c*thickness*5).center(thickness*6))    

#Bottom Pillars
for i in range(thickness+1):
    print((c*thickness).center(thickness*2)+(c*thickness).center(thickness*6))    

#Bottom Cone
for i in range(thickness):
    print(((c*(thickness-i-1)).rjust(thickness)+c+(c*(thickness-i-1)).ljust(thickness)).rjust(thickness*6))
```

## Text Wrap


```python
def wrap(string, max_width):
    l = len(string)
    if l>0 and l<1000 and max_width>0 and max_width<l:
        string = list(string)
        for i in range(l):
            if not i % max_width and i:
                string[i] = '\n' + string[i]
        return ''.join(string)
```

## Designer Door Mat


```python
# Enter your code here. Read input from STDIN. Print output to STDOUT

def odd(i):
    return 2*i+1

def half(oddnumber):
    return (oddnumber+1)/2

N, M = map(int,input().split())
if N>5 and N<101 and M == N*3:
    a = '.|.'
    for i in range(N):
        d = odd(i)
        p = odd(N-1-i)
        h = half(N-2)
        if i < h:
            print((a*d).center(M,'-'))
        elif i > h:
            print((a*p).center(M,'-'))
        else:
            print('WELCOME'.center(M,'-'))
```

## Introduction to Sets


```python
def average(array):
    # your code goes here
    s = set(array)
    n = s.__len__()
    if n>0 and n<=100:
        sum = 0
        for i in s:
            sum += i
        return sum/n
    else:
        return
```

## Alphabet Rangoli


```python
def print_together(left, right, width):
    print( ('-'.join( left + right )).center(width, '-') )

def print_rangoli(size):
    # your code goes here
    if size > 0 and size < 27:
        last = ord('a') + size - 1

        width = 4 * size - 3
        height = 2 * size - 1
        mid_h = size - 1

        lefts = [ [chr(last)] ]
        rights = [ [] ]

        for i in range(1, size):
            rights += [[chr(last)] + rights[i-1]]
            last -= 1
            lefts += [lefts[i-1] + [chr(last)]]
    
        for i in range(size):
            print_together(lefts[i], rights[i], width)
        for i in range(size+1, height+1):
            idx = height - i
            print_together(lefts[idx], rights[idx], width)
```

## Capitalize!


```python
# Complete the solve function below.
def solve(s):
    l = len(s)
    if l>0 and l<1000:
        words = s.split(' ')
        tobeprinted = []
        for word in words:
            tobeprinted += [word.capitalize()]
        return ' '.join(tobeprinted)
```

## Map and Lambda Function


```python
cube = lambda x: x ** 3 # complete the lambda function 

def fibonacci(n):
    # return a list of fibonacci numbers
    if n < 0 or n > 15:
        return
    if n == 0:
        return []
    if n == 1:
        return [0]
    res = [0, 1]
    for i in range(n-2):
        res += [ res[i] + res[i+1] ]
    return res   
```

## ginortS


```python
# Enter your code here. Read input from STDIN. Print output to STDOUT

def QuickSort(lista):
# it's the classical algortihm, not mine

    l = len(lista)

    if l == 1:
        
        return lista

    pivot = lista[0]

    L = []

    R = []

    for i in range(1, l):

        if lista[i] < pivot:

            L += [ lista[i] ]

        else:

            R += [ lista[i] ]

    if L != []:
        
            L = QuickSort(L)

    if R != []:
        
            R = QuickSort(R)

    return L + [pivot] + R






if __name__ == '__main__':
    
    S = list(input())

    l = len(S)

    if l > 0 and l < 1000:

        lower = []

        upper = []

        even = []

        odd = []

        count = 0 # to check the costraints without
        # reading the list again before the for-loop

        for ch in S:

            count += 1

            if count == 1000:
                break

            if ch.isalpha():

                if ch.islower():
                    lower += [ch]

                else:
                    upper += [ch]
    
            if ch.isdigit():

                if int(ch) % 2:
                    odd += [ch]
            
                else:
                    even += [ch]

        if lower != []:
            lower = QuickSort(lower)

        if upper != []:
            upper = QuickSort(upper)

        if odd != []:
            odd = QuickSort(odd)

        if even != []:
            even = QuickSort(even)

        result = lower + upper + odd + even

        print( ''.join(result) )
```
