# Manipulating lists for fun and profit 11/28


```python
#List of food products
frig = ['cheese','bread','milk','eggs']
```


```python
#Extending the list 
frig.extend(['chips','cookies'])
```


```python
#Finding the position of cookies
frig.index('cookies')
```




    5




```python
#Removing the cookies from the list
frig.pop(5)
```




    'cookies'




```python
print(frig)
```

    ['cheese', 'bread', 'milk', 'eggs', 'chips']


# Looping over Lists


```python
#Sorting names of lists
for name in sorted(frig):
    # Print each name
    print(name)
```

    bread
    cheese
    chips
    eggs
    milk



```python
#Empty list
chest = []
```


```python
#List of records example
records = [['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aarya', '10', '40'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Abby', '27', '23'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Abigail', '31', '19'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aisha', '18', '32'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aiza', '19', '31'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Aleena', '17', '33'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alexandra', '11', '39'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alice', '24', '26'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alicia', '12', '38'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alina', '41', '10'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alisa', '11', '39'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alisha', '11', '39'],
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Allison', '15', '35'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Alyssa', '22', '28'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amanda', '15', '35'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amber', '17', '33'], 
 ['2014', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Amelia', '27', '23']]
```


```python
#Adding the 3rds element (index 2) to empty list that has been created 
for row in records:
    chest.append(row[2])
```


```python
#Prints out the 3rd element that is found is the records list
print(chest)
```

    ['ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER', 'ASIAN AND PACIFIC ISLANDER']


# Meet the Tuples



```python
girls = ['JADA','Emily','Ava','SERENITY','Claire','SOPHIA','Sarah','ASHLEY']
guys = ['JOSIAH','ETHAN','David','Jayden','MASON','RYAN','CHRISTIAN','ISAIAH']
```


```python
#Zip for the guys and girls names 
pairs = zip(girls, guys)
```


```python
idx
```




    6



Enumerate function allows you to track the index of the list. 


```python
for idx, pair in enumerate(pairs):
    # Unpack pair: girl_name, boy_name
    girl_name, boy_name = pair
    # Print the rank and names associated with each rank
    print('Rank {}: {} and {}'.format(idx, girl_name, boy_name))
```

    Rank 0: JADA and JOSIAH
    Rank 1: Emily and ETHAN
    Rank 2: Ava and David
    Rank 3: SERENITY and Jayden
    Rank 4: Claire and MASON
    Rank 5: SOPHIA and RYAN
    Rank 6: Sarah and CHRISTIAN
    Rank 7: ASHLEY and ISAIAH


# Sets

Sets only accept unique values. These can be used to identify elements not in one set or it can be used to find matches amoungst different sets.


```python
names = set(['Derek', 'Dayana', 'Meir','Melvin', 'Daphne', 'Jacqueline', 'David', 'Julian', 'Alston', 'Neil', 'Antonio',
 'Allan', 'Ariel', 'Chloe', 'Bryce', 'Alberto', 'Allen', 'Hannah', 'Molly', 'Fatima','Yahya', 'Vanessa','Carmen','Luciana','Rochel','Kyle'])
```


```python
names_2 = set(['Derek', 'Dayana', 'Meir','Melvin', 'Daphne', 'Jacqueline', 'David', 'Julian', 'Alston', 'Neil', 'Antonio',
 'Allan', 'Ariel',])
```


```python
len(names)
```




    26




```python
type(names_2)
```




    set



Union allows you to see all the names within two sets that are unique.


```python
all_names = names.union(names_2)
len(all_names)
```




    26



difference allows you to see non matching elements between two sets.


```python
overlapping = names.difference(names_2)
len(overlapping)
```




    13




```python
intersect = names.intersection(names_2)
```


```python
len(intersect)
```




    13



# Determining set differences


```python
# Create the empty set: baby_names_2011
baby_names_2011 = set()
```


```python
# Loop over records and add the names from 2011 to the baby_names_2011 set
for row in records:
    # Check if the first column is '2011'
    if row[0] == '2014':
        # Add the fourth column to the set
        baby_names_2011.add(row[3])

# Find the difference between 2011 and 2014: differences
differences = baby_names_2011.difference(names)


```


```python
# Print the differences
len(differences)
```




    17




```python
differences
```




    {'Aarya',
     'Abby',
     'Abigail',
     'Aisha',
     'Aiza',
     'Aleena',
     'Alexandra',
     'Alice',
     'Alicia',
     'Alina',
     'Alisa',
     'Alisha',
     'Allison',
     'Alyssa',
     'Amanda',
     'Amber',
     'Amelia'}



# Dictionaries - the root of Python 11/29

- Holds Values in Key value pairs
- Nestable 
- Iterable 
- Dict() or {}
- .get() allows you to access key value pairs 
- Nesting is a common way to deal with repreating data structure


```python
female_baby_names_2012 = {44: 'RIVKY',
 26: 'JULIA',
 43: 'TOBY',
 37: 'MALKY',
 19: 'ABIGAIL',
 25: 'ZOE',
 42: 'PENELOPE',
 39: 'MALKA',
 33: 'SHAINDY'}
```


```python
# Create an empty dictionary: names_by_rank
names_by_rank = {}
```

rank and name act as placeholders for rank (key value) and name (value)


```python
# Loop over the girl names
for rank, name in female_baby_names_2012.items():
    # Add each name to the names_by_rank dictionary using rank as the key
    names_by_rank[rank] = name
```

- sorted is used to sort the values in this case high to low since reverse is set to true
- [:10] grabs the first ten that has been assorted 


```python
# Sort the names_by_rank dict by rank in descending order and slice the first 10 items
for rank in sorted(names_by_rank, reverse=True)[:10]:
    # Print each item
    print(names_by_rank[rank])
```

    RIVKY
    TOBY
    PENELOPE
    MALKA
    MALKY
    SHAINDY
    JULIA
    ZOE
    ABIGAIL



```python
#Printing the key value pair that has number 44 associated with it 
print(names_by_rank.get(44))

```

    RIVKY



```python
#Grabbing key pair value 101 or returning an error message if not found
print(names_by_rank.get(101, 'Not in the dict'))
```

    Not on da list


New dict boys_names


```python
boy_names = {2013: {50: 'Logan',13: 'Henry',54: 'Yaakov',47: 'Yitzchok',49: 'Menachem',32: 'Luke',44: 'Aron',56: 'Omar',
  42: 'Aaron',5: 'Daniel',43: 'Zachary',45: 'Luca',24: 'Anthony',16: 'Nicholas',30: 'Leo',25: 'Isaac',57: 'Levi',19: 'Chaim',
  51: 'Aiden',37: 'Christopher',55: 'Yakov',33: 'Jackson',21: 'Liam',36: 'Joshua',53: 'Peter',38: 'Sebastian',7: 'James',52: 'Yisroel',
  40: 'Eli',27: 'Andrew', 35: 'Theodore',8: 'Jacob',2: 'Joseph',14: 'Noah',34: 'Shimon',46: 'Yehuda',29: 'Yosef',22: 'Ryan',
  9: 'Jack', 1: 'David', 28: 'Gabriel', 48: 'Owen', 26: 'Oliver', 11: 'William', 31: 'Thomas', 23: 'Lucas', 10: 'Alexander', 39: 'Mason', 4: 'Moshe',
  41: 'Nathan', 17: 'Matthew', 12: 'John', 6: 'Benjamin', 20: 'Abraham', 18: 'Adam', 3: 'Michael', 15: 'Samuel', 62: 'Jonah', 61: 'Connor', 60: 'Patrick',
  59: 'Shmuel',58: 'Simon', 79: 'Parker', 82: 'Nicolas', 95: 'Sawyer', 94: 'Yoel', 90: 'Rayan', 73: 'Sean', 85: 'Usher', 92: 'Yossi', 65: 'Nathaniel', 93: 'Wesley', 81: 'Yechiel',
  69: 'Hunter', 76: 'Martin', 74: 'Sam', 87: 'Yusuf', 67: 'Tyler', 88: 'Yehoshua', 84: 'Spencer', 83: 'Timothy', 63: 'Zev',
  86: 'Rafael',91: 'Tristan',89: 'Shaya',71: 'Lipa',66: 'Harrison',68: 'Mark',75: 'Solomon',78: 'Wyatt',80: 'Steven',64: 'Tzvi',
  70: 'Mohamed', 72: 'Mendel', 77: 'Edward', 96: 'Yousef', 100: 'Yitzchak', 99: 'Yeshaya', 97: 'Walter',98: 'Zalmen'}
,2014: {54: 'Aron',14: 'Henry',58: 'Miles',38: 'Andrew',33: 'Eli',42: 'Jackson',51: 'Yitzchok',56: 'Levi', 57: 'Shmuel',
  39: 'Zachary',5: 'Jacob',40: 'Owen',48: 'Asher',26: 'Lucas',21: 'Noah',50: 'Robert',47: 'Jonathan',55: 'Mark',36: 'Mason',
  29: 'Anthony', 45: 'Aiden', 37: 'Mordechai', 53: 'Christian', 18: 'Ethan', 52: 'George', 24: 'Theodore', 34: 'Shimon', 30: 'Oliver',
  7: 'Alexander', 46: 'Christopher', 22: 'Matthew', 9: 'Samuel', 2: 'David',11: 'James', 35: 'Luke', 28: 'Yosef', 44: 'Nathan', 20: 'Ryan', 10: 'Jack', 1: 'Joseph',
  49: 'Logan', 32: 'Gabriel', 17: 'John', 15: 'Abraham', 19: 'Liam', 16: 'Nicholas', 4: 'Moshe',13: 'William',12: 'Adam',27: 'Thomas',
  6: 'Benjamin',23: 'Chaim',41: 'Yehuda',31: 'Max',3: 'Michael',25: 'Isaac',8: 'Daniel',43: 'Yisroel',59: 'Shlomo',60: 'Peter',90: 'Naftali',
  75: 'Shia', 98: 'Yisrael', 88: 'Youssef', 74: 'Oscar', 84: 'Philip', 93: 'Shmiel', 95: 'Naftuli', 68: 'Yakov',96: 'Yusuf', 89: 'Simcha',
  91: 'Ronan',78: 'Tyler',72: 'Edward', 92: 'Usher',69: 'Hunter',85: 'Timothy',80: 'Sam',82: 'Ian',94: 'Yousef', 66: 'Nathaniel',87: 'Xavier',
  97: 'Yossi', 73: 'Yechiel', 67: 'Yaakov', 86: 'Yehoshua', 81: 'Shaya',70: 'Vincent',79: 'Wyatt',61: 'Sean',
  64: 'Gavin',83: 'Raphael',65: 'Zev',62: 'Eliezer', 76: 'Leonardo',77: 'Victor',63: 'Solomon',71: 'Ari',100: 'Yoel',101: 'Yahya',99: 'Shea',102: 'Yidel'},
 2012: {64: 'Gavin'}}
```


```python
# Print a list of keys from the boy_names dictionary
print(boy_names.keys())
```

    dict_keys([2013, 2014, 2012])



```python
# Print a list of keys from the boy_names dictionary for the year 2013
print(boy_names[2013].keys())
```

    dict_keys([50, 13, 54, 47, 49, 32, 44, 56, 42, 5, 43, 45, 24, 16, 30, 25, 57, 19, 51, 37, 55, 33, 21, 36, 53, 38, 7, 52, 40, 27, 35, 8, 2, 14, 34, 46, 29, 22, 9, 1, 28, 48, 26, 11, 31, 23, 10, 39, 4, 41, 17, 12, 6, 20, 18, 3, 15, 62, 61, 60, 59, 58, 79, 82, 95, 94, 90, 73, 85, 92, 65, 93, 81, 69, 76, 74, 87, 67, 88, 84, 83, 63, 86, 91, 89, 71, 66, 68, 75, 78, 80, 64, 70, 72, 77, 96, 100, 99, 97, 98])



```python
# Loop over the dictionary
for year in boy_names:
    # Safely print the year and the third ranked name or 'Unknown'
    print(year, boy_names[year].get(64, 'Unknown'))
```

    2013 Tzvi
    2014 Gavin
    2012 Gavin


# Altering Dictionaries

- .update() adds 
- del will delete keys/values


```python
names_2011 = {51: 'Owen',19: 'Andrew',46: 'Sebastian',36: 'Isaac',38: 'Zachary',52: 'Vincent',
              47: 'Mark',45: 'Yehuda',34: 'Max',7: 'Daniel',30: 'Oliver',18: 'Anthony',22: 'Lucas',
              53: 'Tyler',25: 'Thomas',14: 'John',48: 'Robert',23: 'Dylan',39: 'Leo',16: 'Henry',
              35: 'Shimon',42: 'Jake',28: 'Yosef',37: 'Joshua',27: 'Menachem',50: 'George',49: 'Logan',
              56: 'Yitzchok',55: 'Aidan',10: 'Jack',17: 'Chaim',54: 'Yakov',9: 'Matthew', 1: 'Michael',
              44: 'Yisroel',15: 'Nicholas',21: 'Charles'}
```


```python
# Assign the names_2011 dictionary as the value to the 2011 key of boy_names
boy_names[2011] = names_2011 

# Update the 2012 key in the boy_names dictionary
boy_names[2012].update([(1, 'Casey'), (2, 'Aiden')])
# Loop over the years in the boy_names dictionary 
for year in boy_names:
    # Sort the data for each year by descending rank and get the lowest one
    lowest_ranked =  sorted(boy_names[year], reverse=True)[0]
    # Safely print the year and the least popular name or 'Not Available'
    print(year, boy_names[year].get(lowest_ranked, 'Not Available'))
```

    2013 Yitzchak
    2014 Yidel
    2012 Gavin
    2011 Yitzchok



```python
#Deleting the 2012 key value 
#del boy_names[2012]
```


```python
#Assigning the 2013 names to a seperate variable 
names_2013 = boy_names.pop(2013)
names_2013
```




    {50: 'Logan',
     13: 'Henry',
     54: 'Yaakov',
     47: 'Yitzchok',
     49: 'Menachem',
     32: 'Luke',
     44: 'Aron',
     56: 'Omar',
     42: 'Aaron',
     5: 'Daniel',
     43: 'Zachary',
     45: 'Luca',
     24: 'Anthony',
     16: 'Nicholas',
     30: 'Leo',
     25: 'Isaac',
     57: 'Levi',
     19: 'Chaim',
     51: 'Aiden',
     37: 'Christopher',
     55: 'Yakov',
     33: 'Jackson',
     21: 'Liam',
     36: 'Joshua',
     53: 'Peter',
     38: 'Sebastian',
     7: 'James',
     52: 'Yisroel',
     40: 'Eli',
     27: 'Andrew',
     35: 'Theodore',
     8: 'Jacob',
     2: 'Joseph',
     14: 'Noah',
     34: 'Shimon',
     46: 'Yehuda',
     29: 'Yosef',
     22: 'Ryan',
     9: 'Jack',
     1: 'David',
     28: 'Gabriel',
     48: 'Owen',
     26: 'Oliver',
     11: 'William',
     31: 'Thomas',
     23: 'Lucas',
     10: 'Alexander',
     39: 'Mason',
     4: 'Moshe',
     41: 'Nathan',
     17: 'Matthew',
     12: 'John',
     6: 'Benjamin',
     20: 'Abraham',
     18: 'Adam',
     3: 'Michael',
     15: 'Samuel',
     62: 'Jonah',
     61: 'Connor',
     60: 'Patrick',
     59: 'Shmuel',
     58: 'Simon',
     79: 'Parker',
     82: 'Nicolas',
     95: 'Sawyer',
     94: 'Yoel',
     90: 'Rayan',
     73: 'Sean',
     85: 'Usher',
     92: 'Yossi',
     65: 'Nathaniel',
     93: 'Wesley',
     81: 'Yechiel',
     69: 'Hunter',
     76: 'Martin',
     74: 'Sam',
     87: 'Yusuf',
     67: 'Tyler',
     88: 'Yehoshua',
     84: 'Spencer',
     83: 'Timothy',
     63: 'Zev',
     86: 'Rafael',
     91: 'Tristan',
     89: 'Shaya',
     71: 'Lipa',
     66: 'Harrison',
     68: 'Mark',
     75: 'Solomon',
     78: 'Wyatt',
     80: 'Steven',
     64: 'Tzvi',
     70: 'Mohamed',
     72: 'Mendel',
     77: 'Edward',
     96: 'Yousef',
     100: 'Yitzchak',
     99: 'Yeshaya',
     97: 'Walter',
     98: 'Zalmen'}




```python
# Safely remove 2015 from female_names with an empty dictionary as the default: female_names_2015
# boy_names_2012 gets replaced with an empty dictionary
boy_names_2012 = boy_names.pop(2012, {})
boy_names_2012
```




    {64: 'Gavin', 1: 'Casey', 2: 'Aiden'}



# Pythonically using dictionaries

- in operator checks to see if observation is in the dictionary 


```python
names = {2013: {50: 'Logan',13: 'Henry',54: 'Yaakov',47: 'Yitzchok',49: 'Menachem',32: 'Luke',44: 'Aron',56: 'Omar',
  42: 'Aaron',5: 'Daniel',43: 'Zachary',45: 'Luca',24: 'Anthony',16: 'Nicholas',30: 'Leo',25: 'Isaac',57: 'Levi',19: 'Chaim',
  51: 'Aiden',37: 'Christopher',55: 'Yakov',33: 'Jackson',21: 'Liam',36: 'Joshua',53: 'Peter',38: 'Sebastian',7: 'James',52: 'Yisroel',
  40: 'Eli',27: 'Andrew', 35: 'Theodore',8: 'Jacob',2: 'Joseph',14: 'Noah',34: 'Shimon',46: 'Yehuda',29: 'Yosef',22: 'Ryan',
  9: 'Jack', 1: 'David', 28: 'Gabriel', 48: 'Owen', 26: 'Oliver', 11: 'William', 31: 'Thomas', 23: 'Lucas', 10: 'Alexander', 39: 'Mason', 4: 'Moshe',
  41: 'Nathan', 17: 'Matthew', 12: 'John', 6: 'Benjamin', 20: 'Abraham', 18: 'Adam', 3: 'Michael', 15: 'Samuel', 62: 'Jonah', 61: 'Connor', 60: 'Patrick',
  59: 'Shmuel',58: 'Simon', 79: 'Parker', 82: 'Nicolas', 95: 'Sawyer', 94: 'Yoel', 90: 'Rayan', 73: 'Sean', 85: 'Usher', 92: 'Yossi', 65: 'Nathaniel', 93: 'Wesley', 81: 'Yechiel',
  69: 'Hunter', 76: 'Martin', 74: 'Sam', 87: 'Yusuf', 67: 'Tyler', 88: 'Yehoshua', 84: 'Spencer', 83: 'Timothy', 63: 'Zev',
  86: 'Rafael',91: 'Tristan',89: 'Shaya',71: 'Lipa',66: 'Harrison',68: 'Mark',75: 'Solomon',78: 'Wyatt',80: 'Steven',64: 'Tzvi',
  70: 'Mohamed', 72: 'Mendel', 77: 'Edward', 96: 'Yousef', 100: 'Yitzchak', 99: 'Yeshaya', 97: 'Walter',98: 'Zalmen'}
,2014: {54: 'Aron',14: 'Henry',58: 'Miles',38: 'Andrew',33: 'Eli',42: 'Jackson',51: 'Yitzchok',56: 'Levi', 57: 'Shmuel',
  39: 'Zachary',5: 'Jacob',40: 'Owen',48: 'Asher',26: 'Lucas',21: 'Noah',50: 'Robert',47: 'Jonathan',55: 'Mark',36: 'Mason',
  29: 'Anthony', 45: 'Aiden', 37: 'Mordechai', 53: 'Christian', 18: 'Ethan', 52: 'George', 24: 'Theodore', 34: 'Shimon', 30: 'Oliver',
  7: 'Alexander', 46: 'Christopher', 22: 'Matthew', 9: 'Samuel', 2: 'David',11: 'James', 35: 'Luke', 28: 'Yosef', 44: 'Nathan', 20: 'Ryan', 10: 'Jack', 1: 'Joseph',
  49: 'Logan', 32: 'Gabriel', 17: 'John', 15: 'Abraham', 19: 'Liam', 16: 'Nicholas', 4: 'Moshe',13: 'William',12: 'Adam',27: 'Thomas',
  6: 'Benjamin',23: 'Chaim',41: 'Yehuda',31: 'Max',3: 'Michael',25: 'Isaac',8: 'Daniel',43: 'Yisroel',59: 'Shlomo',60: 'Peter',90: 'Naftali',
  75: 'Shia', 98: 'Yisrael', 88: 'Youssef', 74: 'Oscar', 84: 'Philip', 93: 'Shmiel', 95: 'Naftuli', 68: 'Yakov',96: 'Yusuf', 89: 'Simcha',
  91: 'Ronan',78: 'Tyler',72: 'Edward', 92: 'Usher',69: 'Hunter',85: 'Timothy',80: 'Sam',82: 'Ian',94: 'Yousef', 66: 'Nathaniel',87: 'Xavier',
  97: 'Yossi', 73: 'Yechiel', 67: 'Yaakov', 86: 'Yehoshua', 81: 'Shaya',70: 'Vincent',79: 'Wyatt',61: 'Sean',
  64: 'Gavin',83: 'Raphael',65: 'Zev',62: 'Eliezer', 76: 'Leonardo',77: 'Victor',63: 'Solomon',71: 'Ari',100: 'Yoel',101: 'Yahya',99: 'Shea',102: 'Yidel'},
 2012: {64: 'Gavin'}}
```


```python
for rank, name in names[2013].items():
    # Print rank and name
    print(rank, name)
```

    50 Logan
    13 Henry
    54 Yaakov
    47 Yitzchok
    49 Menachem
    32 Luke
    44 Aron
    56 Omar
    42 Aaron
    5 Daniel
    43 Zachary
    45 Luca
    24 Anthony
    16 Nicholas
    30 Leo
    25 Isaac
    57 Levi
    19 Chaim
    51 Aiden
    37 Christopher
    55 Yakov
    33 Jackson
    21 Liam
    36 Joshua
    53 Peter
    38 Sebastian
    7 James
    52 Yisroel
    40 Eli
    27 Andrew
    35 Theodore
    8 Jacob
    2 Joseph
    14 Noah
    34 Shimon
    46 Yehuda
    29 Yosef
    22 Ryan
    9 Jack
    1 David
    28 Gabriel
    48 Owen
    26 Oliver
    11 William
    31 Thomas
    23 Lucas
    10 Alexander
    39 Mason
    4 Moshe
    41 Nathan
    17 Matthew
    12 John
    6 Benjamin
    20 Abraham
    18 Adam
    3 Michael
    15 Samuel
    62 Jonah
    61 Connor
    60 Patrick
    59 Shmuel
    58 Simon
    79 Parker
    82 Nicolas
    95 Sawyer
    94 Yoel
    90 Rayan
    73 Sean
    85 Usher
    92 Yossi
    65 Nathaniel
    93 Wesley
    81 Yechiel
    69 Hunter
    76 Martin
    74 Sam
    87 Yusuf
    67 Tyler
    88 Yehoshua
    84 Spencer
    83 Timothy
    63 Zev
    86 Rafael
    91 Tristan
    89 Shaya
    71 Lipa
    66 Harrison
    68 Mark
    75 Solomon
    78 Wyatt
    80 Steven
    64 Tzvi
    70 Mohamed
    72 Mendel
    77 Edward
    96 Yousef
    100 Yitzchak
    99 Yeshaya
    97 Walter
    98 Zalmen



```python
# Check to see if 2011 is in baby_names
if 2011 in names:
    # Print 'Found 2011'
    print('Found 2011')
    
# Check to see if rank 1 is in 2012
if 64 in names[2012]:
    # Print 'Found Rank 1 in 2012' if found
    print('Found Rank 64 in 2012')
else:
    # Print 'Rank 1 missing from 2012' if not found
    print('Rank 64 missing from 2012')
    
# Check to see if Rank 5 is in 2013
if 5 in names[2013]:
   # Print 'Found Rank 5'
   print('Found Rank 5')
```

    Found Rank 64 in 2012
    Found Rank 5


Reading CSV


```python
import os
import csv
import pandas as pd
```


```python
os.chdir("Desktop/mojo")
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    Input In [176], in <cell line: 1>()
    ----> 1 os.chdir("Desktop/mojo")


    FileNotFoundError: [Errno 2] No such file or directory: 'Desktop/mojo'



```python
dictionary = {}
```


```python
# Create a python file object in read mode for the baby_names.csv file: csvfile
csvfile = open('names.csv', 'r')

# Loop over a csv reader on the file object
for row in csv.reader(csvfile):
    # Print each row 
    print(row)
    # Add the rank and name to the dictionary
    dictionary[row[2]] = row[2]

# Print the dictionary keys
print(dictionary.keys())
```

    ['\ufeff', 'rank ', 'name']
    ['0', '23', 'Bob']
    ['1', '34', 'Jim']
    ['2', '12', 'Mark']
    ['3', '75', 'Will']
    dict_keys(['name', 'Bob', 'Jim', 'Mark', 'Will'])



```python
for key in dictionary.items():
    print(key)
```

    ('name', 'name')
    ('Bob', 'Bob')
    ('Jim', 'Jim')
    ('Mark', 'Mark')
    ('Will', 'Will')



```python
type(dictionary)
```




    dict



Work on (11/30):
- Figuring out how to read in index properly to column 
- Get values and items in dataframe 


```python
dictionary = {}
```


```python
# Import the python CSV module
import csv

# Create a python file object in read mode for the `baby_names.csv` file: csvfile
csvfile = open('namez.csv', 'r')

# Loop over a DictReader on the file
for row in csv.DictReader(csvfile):
    # Print each row 
    print(row)
    # Add the rank and name to the dictionary: baby_names
    dictionary[row['rank ']] = row['name']

# Print the dictionary keys
print(dictionary.keys())
```

    {'\ufeff': '0', 'rank ': '23', 'name': 'Bob'}
    {'\ufeff': '1', 'rank ': '34', 'name': 'Jim'}
    {'\ufeff': '2', 'rank ': '12', 'name': 'Mark'}
    {'\ufeff': '3', 'rank ': '75', 'name': 'Will'}
    dict_keys(['23', '34', '12', '75'])



```python
pd.DataFrame(list(dictionary.items()),columns = ['rank','name'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rank</th>
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>Bob</td>
    </tr>
    <tr>
      <th>1</th>
      <td>34</td>
      <td>Jim</td>
    </tr>
    <tr>
      <th>2</th>
      <td>12</td>
      <td>Mark</td>
    </tr>
    <tr>
      <th>3</th>
      <td>75</td>
      <td>Will</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
