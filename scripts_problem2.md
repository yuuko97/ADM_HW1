
# ADM Homework 1 Problem 2

## Birthday Cake Candles
Input: 'ar', an array whose elements represents the heights (integers) of some candles, in quantity 'n', an integer taken as input from keyboard in main.

Constraints:    1<= n <= 10^5 ;      1 <= ar[i] <= 10^7 for all i.

Output: number of candles of maximum height.


```python
# !/bin/python3

import math
import os
import random
import re
import sys

# Complete the birthdayCakeCandles function below.
def birthdayCakeCandles(ar):
    
    # Sets the maximum of the array as the first element and then,
    # while counting the occurrences of the last max. stored,
    # changes it and resets the counter if needed.
    
    # Returns the counter.
    
    max = ar[0]
    
    count = 1
    
    for x in ar:
        
        if x == max:
            
            count += 1
            
        elif x > max:
            
            max = ar[i]
            
            count = 1
            
    return count
        
    

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    ar_count = int(input())

    ar = list(map(int, input().rstrip().split()))
    
    # checks the constraints:
    
    # 'flag' becomes 0 iff an element of 'ar' doesn't respect the constraints
    
    if ar_count > 0 and ar_count <= 10**5:
        
        flag = 1
        
        for i in range(ar_count):
        
            if ar[i] < 1 or ar[i] > 10**7:
            
                flag = 0
                
                break
                
        if flag:
            
            result = birthdayCakeCandles(ar)
            
            fptr.write(str(result) + '\n')
            
            fptr.close()

```

## Kangaroo
Inputs: positions x1 and x2 (of two kangaroos),
        velocities v1 and v2

Constraints: positions in range [0, 10^4], x1 < x2
             velocities in range [1, 10^4]

Description of the function kangaroo: calculates the time at which the second kangaroo (in an advanced position) is reached by the first one. If there's no reach or the corresponding time is not an integer, it returns 'NO', otherwise 'YES'.


```python
#!/bin/python3

import math
import os
import random
import re
import sys



def isOk(x, a, b):
# checks whether or not a number x is in the range [a,b]

    if x >= a and x <= b:
        
        return True
    
    return False



# Complete the kangaroo function below.
def kangaroo(x1, v1, x2, v2):
    
    b = 10 ** 4
    
    if isOk(x1, 0, b) and isOk(x2, x1 + 1, b): # constraints
    
        if isOk(v1, 1, b) and isOk(v2, 1, v1 - 1): # constraints
            
            t = (x2 - x1) / (v1 - v2)
            # time of reach, calculated through basic algebra and physics
            
            t_floor = int(t)
            
            if t == float(t_floor):
                
                return 'YES'
            
    return 'NO'


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    x1V1X2V2 = input().split()

    x1 = int(x1V1X2V2[0])

    v1 = int(x1V1X2V2[1])

    x2 = int(x1V1X2V2[2])

    v2 = int(x1V1X2V2[3])

    result = kangaroo(x1, v1, x2, v2)

    fptr.write(result + '\n')

    fptr.close()

```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-4-a9059eab5a3b> in <module>
         34 
         35 if __name__ == '__main__':
    ---> 36     fptr = open(os.environ['OUTPUT_PATH'], 'w')
         37 
         38     x1V1X2V2 = input().split()
    

    C:\ProgramData\Anaconda3\lib\os.py in __getitem__(self, key)
        676         except KeyError:
        677             # raise KeyError with the original key value
    --> 678             raise KeyError(key) from None
        679         return self.decodevalue(value)
        680 
    

    KeyError: 'OUTPUT_PATH'


## Viral Advertising
Input: integer n.
Constraint: 1<= n <= 50
Output: number of people who receive the ad as explained below.

On the first day, the ad is shown to 5 people. Every day after, half of the people who have just received the ad (floored) shares it with 3 friends. We suppose that no one receives the ad more than once.


```python
#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the viralAdvertising function below.
def viralAdvertising(n):
    
    if n > 0 and n < 51:
        
        liked = int(5 / 2)
        
        res = liked # cumulates the likes over the days
        
        for i in range(2,n+1):
            
            liked = int( (liked * 3) / 2 )
            
            res += liked
            
        return res
    
    return ''

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    result = viralAdvertising(n)

    fptr.write(str(result) + '\n')

    fptr.close()

```

## Recursive Digit Sum
Inputs: integers n, k.
Constraints:    1<=n<=10^(10^5),   1<=k<=10^5
Outputs: superdigit of a number p, made by concatenating k times n

The superdigit of x is defined as:
1. x, if its length is 1
2. the superdigit of the sum of the digits of x


```python
#!/bin/python3

import math
import os
import random
import re
import sys

def somma(number):
    # sums the digits of a number casting it from int to list
    n_list = list(str(number))
    s = 0
    for n in n_list:
        s += int(n)
    return s

# Complete the superDigit function below.
def superDigit(n, k):
    # n is a str, k is an int
    
    # The function uses k without creating the number "p" given by
    # concatenating n as a string k times.
    
    # k is used just to multiplicate the sum of the digits of n.
    
    l = len(n)
    
    n_int = int(n)
    
    if n_int > 0 and n_int <= 10**(10**5) and k > 0 and k <= 10**5:
    # conditions over n and k
    
        if l == 1:
            
            if k == 1:
                
                return n_int
            
        s = str( k * somma(n_int) )
        
        return superDigit(s, 1)
    
    return


if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    nk = input().split()

    n = nk[0]

    k = int(nk[1])

    result = superDigit(n, k)

    fptr.write(str(result) + '\n')

    fptr.close()

```

## Insertion Sort - Part 1
Inputs: integer n, array ar of n integer elements.
Constraints:     1<=n<=1000,     -10000<=arr[i]<=10000 for all i.

The array is almost ordered in the sense that only the last element may not be ordered.
It has to be put in the right place - so that the array is ordered - in this way:
at first, the number is stored, then all the digits from the right are moved to the right one-by-one.

Output: at every shift and at the insertion the ar is printed.


```python
#!/bin/python3

import math
import os
import random
import re
import sys

def inRange(number, a, b):
    if number >= a and number <= b:
        return True
    return False

# Complete the insertionSort1 function below.
def insertionSort1(n, arr):
    b = 10000
    a = - b
    if inRange(n, 1, 1000) and inRange(arr[0], a, b):
        
        # if there's just one element, it is in the right position
        if n == 1:
            return
        
        # otherwise I store the last element, as required
        x = arr[n-1]
        
        # given the precondition that the array is almost ordered,
        # I check only the first (done before) and last elements that should be,
        # plus the element that should be placed correctly (arr[n-1]=x)
        if inRange(arr[n-2], a, b) and inRange(x, a, b):
            
            if arr[n-2] < x: # in this case I mustn't move x
                return
            
            pos = 0 # just to initialize pos
            
            # in the cases left x has to be moved, so I check from arr[0] to arr[n-1]
            for i in range(n-1):
                
                if arr[i] < x:
                    
                    pos = i + 1
                else:
                    
                    break
            
            # now I copy one element at a time, beginning from the last to move before arr[n-1]
            # and using the fact that arr[n-1] is already stored
            i = n - 2
            
            while i >= pos:
                
                arr[i+1] = arr[i]
                
                print(' '.join(map(str, arr)))
                
                i -= 1
                
            arr[pos] = x
            
            print(' '.join(map(str, arr)))
        

if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))

    insertionSort1(n, arr)

```

## Insertion Sort - Part 2
This is an evolution of the previous part.
The inputs and the constraints are the same, but the array may be totally unordered.
The Part 1 is applied recursively to a progressively bigger sublist of the array.

Output: the array has to be printed every time a change in the order occurs.


```python
#!/bin/python3

import math
import os
import random
import re
import sys

def inRange(number, a, b):
# function to check numbers in a range
    if number >= a and number <= b:
        return True
    return False

def arrInRange(arr, a, b):
# function to check lists in range
    for n in arr:
        if not inRange(n, a, b):
            return False
    return True

def insertionSort1(n, arr):
# see the previous exercise, I just put the checking in insertionSort2
# and inserted some prints where needed (every time a sublist has been ordered,
# even with no shuffles)
    if n == 1:
        print(' '.join(map(str, arr)))
        return
    x = arr[n-1]
    if arr[n-2] < x:
        print(' '.join(map(str, arr)))
        return
    pos = 0
    for i in range(n-1):
        if arr[i] < x:
            pos = i + 1
        else:
            break
    i = n - 2
    while i >= pos:
        arr[i+1] = arr[i]
        i -= 1
    arr[pos] = x
    print(' '.join(map(str, arr)))

# Complete the insertionSort2 function below.
def insertionSort2(n, arr):
    
    if inRange(n, 1, 1000) and arrInRange(arr, -10000, 10000):
        
        for i in range(2, n+1):
            
            insertionSort1(i, arr)


if __name__ == '__main__':
    n = int(input())

    arr = list(map(int, input().rstrip().split()))

    insertionSort2(n, arr)

```
