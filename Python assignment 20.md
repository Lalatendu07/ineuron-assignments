#### 1. Set the variable test1 to the string &#39;This is a test of the emergency text system,&#39; and save test1 to a file named test.txt.


```python
test1='This is a test of the emergency text system,'
with open('test.txt','w') as file:
    file.write(test1)
    file.close()
```

#### 2. Read the contents of the file test.txt into the variable test2. Is there a difference between test 1 and test 2?


```python
with open('test.txt','r') as file:
    test2=file.read()
    print(test2)
    print(test1)
```

    This is a test of the emergency text system,
    This is a test of the emergency text system,
    

No difference.

#### 3. Create a CSV file called books.csv by using these lines:
`title,author,year`  
`The Weirdstone of Brisingamen,Alan Garner,1960`  
`Perdido Street Station,China Miéville,2000`  
`Thud!,Terry Pratchett,2005`  
`The Spellman Files,Lisa Lutz,2007`  
`Small Gods,Terry Pratchett,1992`


```python
data='''title,author,year
The Weirdstone of Brisingamen,Alan Garner,1960
Perdido Street Station,China Miéville,2000
Thud!,Terry Pratchett,2005
The Spellman Files,Lisa Lutz,2007
Small Gods,Terry Pratchett,1992'''

with open('books.csv','w') as file:
    file.write(data)
```

#### 4. Use the sqlite3 module to create a SQLite database called books.db, and a table called books with these fields: title (text), author (text), and year (integer).


```python
import sqlite3
db = sqlite3.connect('Books.db')
cr = db.cursor()
cr.execute("CREATE TABLE if not exists Book (title text, author text, year int)")
db.commit()
db.close()
```

#### 5. Read books.csv and insert its data into the book table.


```python
import sqlite3
import csv
db = sqlite3.connect("Books.db")
cr = db.cursor()
with open("books.csv","r") as file:
    Book = csv.DictReader(file)
    for book in Book:
        cr.execute("INSERT INTO Book VALUES (?,?,?)",(book['title'],book['author'],book['year']))
db.commit()
db.close()
```

#### 6. Select and print the title column from the book table in alphabetical order.


```python
import sqlite3
db = sqlite3.connect('Books.db')
cr = db.cursor()
output = cr.execute("SELECT title FROM Book ORDER BY title ASC")
for i in output:
    print(i[0])
db.commit()
db.close()
```

    Perdido Street Station
    Small Gods
    The Spellman Files
    The Weirdstone of Brisingamen
    Thud!
    

#### 7. From the book table, select and print all columns in the order of publication.


```python
import sqlite3
db = sqlite3.connect('Books.db')
cr = db.cursor()
ouput = cr.execute("SELECT * FROM Book ORDER BY year")
for record in ouput:
    print(record)
```

    ('The Weirdstone of Brisingamen', 'Alan Garner', 1960)
    ('Small Gods', 'Terry Pratchett', 1992)
    ('Perdido Street Station', 'China Miéville', 2000)
    ('Thud!', 'Terry Pratchett', 2005)
    ('The Spellman Files', 'Lisa Lutz', 2007)
    

#### 8. Use the sqlalchemy module to connect to the sqlite3 database books.db that you just made in exercise 6.


```python
import sqlalchemy
conn = sqlalchemy.create_engine('sqlite:///Books.db')
conn
```




    Engine(sqlite:///Books.db)



#### 9. Install the Redis server and the Python redis library (pip install redis) on your computer. Create a Redis hash called test with the fields count (1) and name (&#39;Fester Bestertester&#39;). Print all the fields for test.


```python
pip install redis
```

    Requirement already satisfied: redis in c:\users\user\anaconda3\lib\site-packages (4.3.4)
    Requirement already satisfied: async-timeout>=4.0.2 in c:\users\user\anaconda3\lib\site-packages (from redis) (4.0.2)
    Requirement already satisfied: deprecated>=1.2.3 in c:\users\user\anaconda3\lib\site-packages (from redis) (1.2.13)
    Requirement already satisfied: packaging>=20.4 in c:\users\user\anaconda3\lib\site-packages (from redis) (21.3)
    Requirement already satisfied: wrapt<2,>=1.10 in c:\users\user\anaconda3\lib\site-packages (from deprecated>=1.2.3->redis) (1.12.1)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in c:\users\user\anaconda3\lib\site-packages (from packaging>=20.4->redis) (3.0.4)
    Note: you may need to restart the kernel to use updated packages.
    


```python
import redis
conn = redis.Redis()
conn.hset('test',{ 'count':1,'name':'Fester Bestertester'})
conn.hgetall('test')
```

#### 10. Increment the count field of test and print it.


```python
conn.hincrby('test', 'count', 1)
conn.hget('test', 'count')
```




    b'13'




```python

```
