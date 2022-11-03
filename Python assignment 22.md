#### 1. What is the result of the code, and explain?

&gt;&gt;&gt; X = &#39;iNeuron&#39;

&gt;&gt;&gt; def func():

    print(X)

&gt;&gt;&gt; func()


```python
>>> X = 'iNeuron'
>>> def func():
      print(X)
>>> func()
```

    iNeuron
    

Ans: The Result of this code is iNeuron, it's because the function intially looks for the variable X in its local scope,But since there is no local variable X, its returns the value of global variable X i.e. iNeuron.

#### 2. What is the result of the code, and explain?

&gt;&gt;&gt; X = &#39;iNeuron&#39;

&gt;&gt;&gt; def func():
    
X = &#39;NI!&#39;

&gt;&gt;&gt; func()

&gt;&gt;&gt; print(X)


```python
>>> X = 'iNeuron'
>>> def func():
     X = 'NI!'

>>> func()
>>> print(X)
```

    iNeuron
    

Ans. The global variables are access in side the functions in python. But we can not access function variable out side function.
Since X is golbal variable we are able to print it out side of the function solution = 'iNeuron'

#### 3. What does this code print, and why?

&gt;&gt;&gt; X = &#39;iNeuron&#39;

&gt;&gt;&gt; def func():

X = &#39;NI&#39;

print(X)

&gt;&gt;&gt; func()

&gt;&gt;&gt; print(X)


```python
>>> X = 'iNeuron'
>>> def func():
        X = 'NI'
        print(X)

>>> func()
>>> print(X)
```

    NI
    iNeuron
    

Ans. The global variables are accessible in side the functions in python. But we can not access function variable out side function.
X is updated with 'NI' which is local to function and its immutable. its name space is with in the function solution = 'NI!', 'iNeuron'

#### 4. What output does this code produce? Why?

&gt;&gt;&gt; X = &#39;iNeuron&#39;

&gt;&gt;&gt; def func():

global X

X = &#39;NI&#39;

&gt;&gt;&gt; func()

&gt;&gt;&gt; print(X)


```python
>>> X = 'iNeuron'
>>> def func():
    global X
    X = 'NI'

>>> func()
>>> print(X)
```

    NI
    

Ans. Since the X in side function is made Global, it will be accesible out side of the function too. 
Initially X='iNeuron' ,now X will have new value 'IN'.

#### 5. What about this code—what’s the output, and why?

&gt;&gt;&gt; X = &#39;iNeuron&#39;

&gt;&gt;&gt; def func():

X = &#39;NI&#39;

def nested():

print(X)

nested()

&gt;&gt;&gt; func()

&gt;&gt;&gt; X


```python
>>> X = 'iNeuron'
>>> def func():
    X = 'NI'

def nested():
    print(X)

nested()
>>> func()
>>> X
```

    iNeuron
    




    'iNeuron'



Ans. The nested() function will print 'iNeuron', Then func() does not display anything, and x ='NI' is not accessible out side the function.

#### 6. How about this code: what is its output in Python 3, and explain?

&gt;&gt;&gt; def func():
    
X = &#39;NI&#39;

def nested():

    nonlocal X

    X = 'Spam'

    nested()

    print(X)

&gt;&gt;&gt; func()


```python
>>> def func():
        X = 'NI'
    
        def nested():
            nonlocal X
            X = 'Spam'

        nested()
        print(X)
>>> func()
```

    Spam
    

Ans. Nonlocal variables are used in nested functions whose local scope is not defined. 
This means that the variable can be neither in the local nor the global scope it print the updated value from nested function.


```python

```
