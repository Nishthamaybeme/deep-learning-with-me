#oops
Here’s a detailed explanation of Object-Oriented Programming (OOP) concepts demonstrated in the provided code, organized to cover the foundational pillars of OOP: classes and objects, constructors, attributes, methods, encapsulation, access modifiers, and static methods. Additionally, it highlights OOP’s four main principles: **Abstraction**, **Encapsulation**, **Inheritance**, and **Polymorphism**.

---

### **1. Classes and Objects**

   - **Class**: A class is a blueprint for creating objects. It defines a set of attributes (data) and methods (functions) that the objects created from the class will have.
   - **Object**: An instance of a class with its own distinct state, created by calling the class as if it were a function.

   **Example**:
   ```python
   class Student1:
       name = "nishtha"  # Attribute (data) defined within the class
   s1 = Student1()  # s1 is an object of the class Student1
   print(s1.name)   # Output: nishtha
   ```

---

### **2. Constructors**

   - A **constructor** in Python is a special method called `__init__` used for initializing a new object. 
   - When you create an object from a class, the constructor is automatically executed.
   - There are two types of constructors demonstrated:
     - **Default Constructor**: Initializes the object without parameters.
     - **Parameterized Constructor**: Initializes the object with parameters to set initial attribute values.

   **Example**:
   ```python
   class Student2:
       def __init__(self, fullname):  # Parameterized constructor
           self.name = fullname
           print("Adding new student in the database")

   s1 = Student2("nishtha")
   print(s1.name)  # Output: nishtha
   ```

---

### **3. Attributes (Data Members)**

   - **Attributes** are variables stored in a class. They can be shared across all instances (class attributes) or unique to each instance (instance attributes).
   - **Class Attributes**: Shared among all objects of the class.
   - **Instance Attributes**: Unique to each object, typically defined within the constructor using `self`.

   **Example**:
   ```python
   class Student4:
       collegename = "DEI College"  # Class attribute, shared by all instances
       def __init__(self, name):
           self.name = name  # Instance attribute, unique to each object

   s1 = Student4("nishtha")
   s2 = Student4("alice")
   print(s1.collegename)  # Output: DEI College (shared class attribute)
   print(s1.name)         # Output: nishtha (unique instance attribute)
   ```

---

### **4. Methods**

   - **Methods** are functions defined within a class that operate on the object’s attributes.
   - **Instance Methods**: Require `self` as the first parameter to access the instance’s attributes and other methods.
   - Methods can also be used to perform calculations, modify data, or perform any operation on the object.

   **Example**:
   ```python
   class Student:
       def __init__(self, name, marks):
           self.name = name
           self.marks = marks

       def welcome(self):
           print("Welcome", self.name)

       def get_marks(self):
           return self.marks

   s1 = Student("nishtha", 21)
   s1.welcome()           # Output: Welcome nishtha
   print(s1.get_marks())   # Output: 21
   ```

---

### **5. Static Methods**

   - **Static Methods**: Defined using the `@staticmethod` decorator and do not use `self`. They belong to the class rather than an instance and operate independently of any object-specific data.
   - Useful for utility functions related to the class but not needing instance data.

   **Example**:
   ```python
   class Student:
       @staticmethod
       def hello():
           print("Hello, world")

   Student.hello()  # Output: Hello, world
   ```

---

### **6. Encapsulation**

   - **Encapsulation** is the concept of restricting direct access to certain elements of an object, often achieved through private attributes.
   - **Public Attributes**: Can be accessed freely.
   - **Private Attributes**: Prefixed with double underscores (`__`) and meant for internal use within the class.

   **Example**:
   ```python
   class Account:
       def __init__(self, acc_no, password):
           self.acc_no = acc_no          # Public attribute
           self.__password = password    # Private attribute

       def reset_pass(self):
           print(self.__password)

   acc1 = Account("122", "232")
   acc1.reset_pass()  # Output: 232
   ```

   - **Encapsulation** ensures sensitive information is hidden from outside interference and only accessible through specific methods.

---

### **7. Access Modifiers**

   - In Python, access modifiers are indicated by name conventions:
     - **Public**: No underscore prefix.
     - **Private**: Two underscores (e.g., `__password`).
   - Attempting to access private attributes outside the class will raise an `AttributeError`.

   **Example**:
   ```python
   class Person:
       __name = "anonymous"  # Private attribute

       def get_name(self):
           return self.__name  # Accessing private attribute via a public method

   p1 = Person()
   print(p1.get_name())  # Output: anonymous
   ```

---

### **8. OOP Principles**

   - **Abstraction**: Hiding unnecessary details and showing only essential features. In the code, methods like `reset_pass` give limited access to password data.
   - **Encapsulation**: Restricting access to private data, as seen with private variables like `__password`.
   - **Inheritance**: Not shown in this code, but it allows creating a new class based on an existing class, enabling code reuse.
   - **Polymorphism**: Allows using a single interface for different data types. Example not provided in this code, but it’s often achieved with method overriding or interfaces.

---

### **9. Using the `del` Keyword**

   - **`del` Keyword**: Used to delete objects or attributes, freeing up memory.
   - When you delete an object, Python’s garbage collector frees the associated memory.

   **Example**:
   ```python
   s1 = Student("nishtha", [33, 33, 23])
   del s1  # Deletes the object s1 from memory
   ```

---

### **Summary**

This code provides a comprehensive look at Object-Oriented Programming in Python:

1. **Classes and Objects**: How classes serve as blueprints and objects as instances.
2. **Constructors**: Both default and parameterized constructors to initialize objects.
3. **Attributes**: Differentiation between class attributes and instance attributes.
4. **Methods**: Including instance methods and static methods, demonstrating how behavior is defined within classes.
5. **Encapsulation**: With private and public access modifiers, emphasizing controlled access.
6. **Principles of OOP**: Demonstrating abstraction, encapsulation, and setting up for inheritance and polymorphism.
# class Student1:   # class 
#     name="nishtha"
# # class is a blueprint (like we get the information of students to fill the classes in our school)
# s1=Student1()  # s1 is an object of the class Student

# # now the objects are the actual students in our school

# # print(s1.name)  # Output: nishtha
# # class Car:
# #     color="blue"
# #     brand="mercedes"
# # car1 = Car()
# # print(car1.color)
# # print(car1.brand)

# #constructor 
# # when a new object is created a constructor is executed 
# # python automatically  calls the constructor when we create a new object
# class  Student2:
#     def __init__(self):
#         pass    #  this one above is a default constructor 
#     def  __init__(self,fullname):  # constructor
#         self.name=fullname
#         print("adding new student in the db")
#         # this one above is a parameterised constructor 

# # cosntructor always take a self parameter  which is a reference to the current instance(object) of the class and is used to access variables and methods from

# s1=Student2("nishtha")
# print(s1.name)
# # all data stored or variables are called attributes  of the class
# # the constructor written at last would override the before constructors 
# # and we should always make one constructor 
# # # Summary
# # Single Constructor: In Python, only one __init__ method can be defined. If you define multiple, the last one will override the previous ones.
# # Parameter Matching: To allow for different types of instantiation (like using different parameters), use default arguments or variable-length arguments to handle multiple cases without needing to define multiple constructors.
# # Error Handling: It's always good practice to handle potential errors, such as an incorrect number of arguments.
# class Student3:
#     def __init__(self, *args):  # Accept any number of arguments
#         if len(args) == 2:  # Expecting two arguments (name, age)
#             self.name = args[0]
#             self.age = args[1]
#             print("Adding new student with age to the database.")
#         elif len(args) == 1:  # Expecting one argument (name)
#             self.name = args[0]
#             self.age = None
#             print("Adding new student without age to the database.")
#         else:
#             raise ValueError("Invalid number of arguments.")

# # Examples of instantiation
# s1 = Student3("Nishtha", 54)  # Calls the constructor with two arguments
# print(s1.name, s1.age)

# s2 = Student3("Alice")  # Calls the constructor with one argument
# print(s2.name, s2.age)
# # in the above code we saw how we can use single constructor for handling multiple parametered output without creating multiple constructors also if we make multiple constructor it will override the earlier once ands execute the latter one only


# #attributes
# # attributes are the data stored in the class
# # class attributes common for all object
# # instance attributes are specific to each object( different for each object)

# # student(class)
# # s1 s2 s3 s4 
# # name name name name isnt name supposed to be an instance attribute 
# # different for diff object  
# # self is used for object attributes  self.name for example is an instance/class attribute 
# # but the name of college will be same for all students so it is a class attribute 
# class Student4:
#     collegename="dei college"
#     name="annonymous"
#     def __init__(self,name):
#         self.name=name
#     # if we have a same name of instance and class attributes  then the instance attribute will be executed first as it has high precedence 



# s1=Student4("nishtha")
# s2=Student4("nishtha")
# print(s2.collegename)
# # in the above code we saw how we can use class attributes and instance attributes in python
# #  class attributes are common for all objects and instance attributes are specific to each object
# #   self is used for instance attributes and class attributes are defined outside the constructor
# #     class attributes are defined outside the constructor and instance attributes are defined inside the constructor
# #ccollegename took only one space int he memory whielname is diff for everys tudent so it takes difefernt spaces in the memory 

# print(s1.name)
# print(Student4.collegename)

# #######METHODS ########3
# # I A CLASS TWO THINGS ARE STORED ATTRIVUTES AND METHODS 
# METHODS ARE THE FUNCTIONS DEFINED INSIDE THE CLASS
# ATTRIBUTES ARE THE DATA STORED 
# METHODS ARE BASICALLY FUNCTIONS THAT BELONGS TO OBJECTS 
class Student :

    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def welcome(self): #this is a method or u can say a fucntion  inside a class
        print("welcome",self.name)
        
    def get_marks(self):
        return self.marks
    

s1=Student("nishtha",21)
s1.welcome() #this is how wecall a method inside a class

print(s1.get_marks()) #this is how we call a method inside a class


class Student:
    def __init__(self,name,marks):
        self.name=name
        self.marks=marks

    def get_avg(self):
        sum=0
        for val in self.marks:
            sum+=val
        print("hi", self.name ," ur avg is ",sum/3)


   
    
s1=Student("nishsin",[33,33,23])
s1.name="nishbish"
s1.get_avg()
del s1

#normal methods above

# now static method are introduced 
# static methods are the methods that belongs to class not to objects
# they are used to perform some operation on class level not on object level
# the dont have self parameter and work at class level not object level

# class Student:
#     # @staticmethod
#     def hello():
#         print("hello"
#               "world")
#         # calling static method
# s1=Student( )
# s1.hello()
# decorator is modfiiying the function which chnages the behavior of a normal function 
# decorators are used to add some extra functionality to the existing function without changing it
# oops have four pillars
# abstraction encapsulation
# inerhtience and polymorphsom
# abstraction is hiding unnecessary things from the user 

#del keywword used to delete
# private  and public 

# above s1 is public
class Account:
    def __init__(self,accno,password):
        self.acc_no=accno#public variable
        self.__password=password # private variable
    def reset_pass(self):
        print(self.__password)    

acc1=Account("122","232")
# print(acc1.__password)# we cant access it outside class
print(acc1.reset_pass())
# encapsulation is hiding the data from the outside world and showing only the methods to access it

class PErson:
    __name="annoymous"

    def __hello():print("bello")

p1=PErson()
print(p1.__name)
print(p1.__hello())
With these elements, this code provides a strong understanding of OOP, setting the stage for more complex patterns and structures in software development.
