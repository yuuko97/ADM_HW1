
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
