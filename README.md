# PIAIC-132123-AI-Assignment-2
PIAIC AI Assignment 2 Task 1 &amp; 2
'''
ASSIGNMENT # 2 :
1- To make Class-parents and child
2- Operator Overloading
Sheeraz Ali Sabri
PIAIC 132123
Batch 36
Instructor : Sir Qasim

Task 1:
Import Father & Mother attribute and add two new attributes in the Child constructor
'''

# creating Father class
class Father:
  def __init__(self, name, age):
    self.name = name
    self.age = age
    
  def showFather(self):
    return f"My name is {self.name}, I am {self.age} years old"
f1 = Father("Sheeraz", 58)
print(f1.showFather())
print([i for i in dir(f1) if "__" not in i])

#Creating Mother class
class Mother:
  def __init__(self, language, job):
    self.language = language
    self.job = job
  
  def showMother(self):
    return f"My mother tounge is {self.language} and I am a {self.job}."
m1 = Mother("Urdu", "housewife")
print(m1.showMother())
print([i for i in dir(m1) if "__" not in i])

#Creating Child class
class Child(Father,Mother):
  def __init__(self,name,age,language, education):
    Father.__init__(self, name, age)
    Mother.__init__(self, language, education)
    self.gender = None
    self.hobby = None

  def showSelf(self):
    return (Father.showFather(self) + f" and I am a {self.gender}. "+ Mother.showMother(self)+ f" I like {self.hobby}")

c1 = Child("Shees", 16, "Urdu", "class X student")
c1.gender = "boy"
c1.hobby = "reading"
print(c1.showSelf())
print([i for i in dir(c1) if "__" not in i])

'''
Task 2:
Create operator overloading
'''

class item:
  def __init__(self,name,price):
    self.price = price
    self.name = name
  def __add__(first, second):
    x = first.price+second.price
    return x

item1 = item("books", 1000)
item2 = item("calculator",350)
print(item1+item2)
