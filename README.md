# hacker-rank-python-programs
# Search With Unique name of the question and then search with Starting of the Question ( some question does not  have heading and a unique name search them by the start) 



### Given the names and grades for each student in a class of  students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade. ( Nested Lists )
```
if __name__ == '__main__':
    records = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        records.append([name,score])
    records.sort(key=lambda item: item[1])
    sorted_list_in_reverse = [*records]
    ans_marks = 0
    ans_names = []
    start = 1
    min_main = sorted_list_in_reverse[0][1]
    for index,item in enumerate(sorted_list_in_reverse[1:len(sorted_list_in_reverse)]):
        if item[1] == min_main:
            start = start+1
        else:
            break
    for ans in sorted_list_in_reverse[start:len(sorted_list_in_reverse)]:
        if ans_marks == 0:
            ans_marks = ans[1]
            ans_names.append(ans[0])
        else:
            if  ans_marks == ans[1]:
                ans_names.append(ans[0])
            else:
                break
    ans_names.sort(key=lambda item: item[0])
    print("\n".join(i for i in ans_names))
    
```


### Transpose and Flatten
### We can generate the transposition of an array using the tool .
```
import numpy
n, m = map(int, input().split())
array = numpy.array([input().strip().split() for _ in range(n)], int)
print (array.transpose())
print (array.flatten())

```

### Time Delta
### When users post an update on social media,such as a URL, image, status update etc., other users in their network are able to view this new post on their news feed. Users can also see exactly when the post was published, i.e, how many hours, minutes or seconds ago.

```
#!/bin/python3

import math
import os
import random
import re
import sys
from datetime import datetime

# Complete the time_delta function below.
def time_delta(t1, t2):
    date1= datetime.strptime(t1,"%a %d %b %Y %H:%M:%S %z")
    date2= datetime.strptime(t2,"%a %d %b %Y %H:%M:%S %z")
    return str(int(abs((date1-date2).total_seconds())))   
    
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    t = int(input())

    for t_itr in range(t):
        t1 = input()

        t2 = input()
        
        delta = time_delta(t1, t2)

        fptr.write(str(delta)+"\n")

    fptr.close()

```


### Validating Email Addresses With a Filter


### You are given an integer n followed by m email addresses. Your task is to print a list containing only valid email addresses in lexicographical order.

```
import re
def fun(s):
    # print(s)
    # return True if s is a valid email, else return False
    pat = r'\b[A-Za-z0-9_-]+@[A-Za-z0-9]+\.[A-Za-z]{1,3}\b'
    return re.match(pat,s)
    
def filter_mail(emails):
    return list(filter(fun, emails))

if __name__ == '__main__':
    n = int(input())
    emails = []
    for _ in range(n):
        emails.append(input())

filtered_emails = filter_mail(emails)
filtered_emails.sort()
print(filtered_emails)
```

### Map and Lambda Function
###Let's learn some new Python concepts! You have to generate a list of the first  fibonacci numbers,  being the first number. Then, apply the map function and a lambda expression to cube each fibonacci number and print the list.

```
cube = lambda x: x*x*x
def fibonacci(n):
    # Write your code here.
    lis = [0,1]
    
    # for loop starting from 2
    for i in range(2,n):
        lis.append(lis[i-2] + lis[i-1])
    return(lis[0:n])

```

### Reduce Function
### Given a list of rational numbers,find their product.

```
from fractions import Fraction
from functools import reduce
from fractions import gcd
def product(fracs):
    t = Fraction(reduce(lambda x,y : x*y,fracs))
    return t.numerator, t.denominator


```

### Finding the percentage
### The provided code stub will read in a dictionary containing key/value pairs of name:[marks] for a list of students. Print the average of the marks array for the student name provided, showing 2 places after the decimal.

```
if __name__ == '__main__':
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    list_of_marks = student_marks[query_name]
    avg = sum(list_of_marks)/len(list_of_marks)
    print(format(avg,".2f"))

```

### Designer Door Mat
###Mr. Vincent works in a door mat manufacturing company. One day, he designed a new door mat with the following specifications:

```
def get_odd_num(end):
    # iterating each number in list
    number = -3
    start = 1
    for num in range(start, end ):

        # checking condition
        if num % 2 != 0:
            # print_start(num,num*3,number)
            number=number+1
    return  number

x, y = list(map(int, input().split()))
obj=get_odd_num(x)

for i in range(1, x // 2 + 1):

    if (x // 2) + 1 > i:
        h = (y // 2)
        z = ("."+'|'+'.') * (i - 1) +("."+'|'+'.')  + ("."+'|'+'.') * (i - 1)
        print("-" * (h - len(("."+'|'+'.') * (i - 1)) - 1) + z + "-" * (h - len(("."+'|'+'.') * (i - 1)) - 1))

print("WELCOME".center(y, "-"))
j = obj
for i in range(x // 2 + 2, x + 1):
    z = ('.'+'|'+'.') * ((x // 2) + 2 + j)
    print(z.center(y, "-"))
    j -= 2

```

###Find the Runner-Up Score!

###Given the participants' score sheet for your University Sports Day, you are required to find the runner-up score. You are given  scores. Store them in a list and find the score of the runner-up.

```
if __name__ == '__main__':
    n = int(input())
    arr = list(map(int, input().split()))
    

l=[]

for i in arr:
    if i not in l:
        l.append(i)
        
x= max(l)
l.remove(x)
print(max(l))

```

### Print Function
###

```
n = int(input())
t=""
for i in range(1,n+1):

    t=t+str(i)
    
print(t)


```

###Write a function


###

```
def is_leap(year):
    if (year %400)==0:
        year="leap"
    elif (year %100)==0:
         year="not leap"
    elif (year %4)==0:
         year="leap"
    else:
        pass
    if year=="leap":
        return True
    else:
        return False
        

```

###Loops
###

```
n = int(input())
for i in range(n):
    print(i*i)

```

###Python: Division
###

```
a = int(input())
b = int(input())
print(a//b)
print(a/b)

```

###Arithmetic Operators


###

```
a = int(input())
b = int(input())
print(a+b)
print(a-b)
print(a*b)

```


### Python If-Else
###

```

n=int(input())
if (n%2)!=0:
    print('Weird')
elif n==2 or n==4:
    print('Not Weird')
elif n>=6 and n<=20:
    print('Weird')
else:
    print('Not Weird')

```

### Say "Hello, World!" With Python
###

```
if __name__ == '__main__':
    print "Hello, World!"

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```


###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```



###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```



###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```

###
###

```

```
