#### 1. Write a Python program to print &quot;Hello Python&quot;?


```python
print('Hello Python')
```

    Hello Python
    

#### 2. Write a Python program to do arithmetical operations addition and division.?


```python
while True:
    ops=input('enter any one + or /')

    if ops=='+':
        num1=int(input('enter 1st number'))
        num2=int(input('enter 2nd number'))
        a= num1+num2
        print(num1,'+',num2,'=',a)
    elif ops=='/':
        num1=int(input('enter 1st number'))
        num2=int(input('enter 2nd number'))
        d= num1/num2
        print(num1,'/',num2,'=',d)
    else:
        print('enter valid operators i.e.+ or /')
        break
```

    enter any one + or /+
    enter 1st number1000
    enter 2nd number500
    1000 + 500 = 1500
    enter any one + or //
    enter 1st number200
    enter 2nd number50
    200 / 50 = 4.0
    enter any one + or /*
    enter valid operators i.e.+ or /
    

#### 3. Write a Python program to find the area of a triangle?


```python
h=int(input('Enter the height of the triangle'))
b=int(input('Enter the base of the triangle'))

def area_of_tri(h,b):
    print('Area of triangle =',0.5*b*h)
    
area_of_tri(h,b)    
```

    Enter the height of the triangle100
    Enter the base of the triangle200
    Area of triangle = 10000.0
    

#### 4. Write a Python program to swap two variables?


```python
num1=int(input('enter 1st number'))
num2=int(input('enter 2nd number'))

def swapnum(n1,n2):
    temp = n1
    n1 = n2
    n2 = temp
    return n1,n2

print('Before swaping : ',num1 , num2)
num1,num2=swapnum(num1,num2)
print('After swaping : ',num1 , num2)
```

    enter 1st number250
    enter 2nd number450
    Before swaping :  250 450
    After swaping :  450 250
    

#### 5. Write a Python program to generate a random number?


```python
from random import randint

def RandNum(a , b):
    print('Random number :',randint(a,b))
    
RandNum(0 , 100)
```

    Random number : 35
    


```python

```
