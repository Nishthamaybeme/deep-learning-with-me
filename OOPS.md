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

With these elements, this code provides a strong understanding of OOP, setting the stage for more complex patterns and structures in software development.
