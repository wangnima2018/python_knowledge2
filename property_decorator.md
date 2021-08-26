```python
https://www.tutorialsteacher.com/python/property-decorator

Property Setter
Above, we defined the name() method as a property. We can only access the value of the name property but cannot modify it. To modify the property value, we must define the setter method for the name property using @property-name.setter decorator, as shown below.

Example: Property Setter Copy
class Student:

    def __init__(self, name):
        self.__name=name

    @property
    def name(self):
        return self.__name

    @name.setter   #property-name.setter decorator
    def name(self, value):
        self.__name = value
Above, we have two overloads of the name() method. One is for the getter and another is the setter method. The setter method must have the value argument that can be used to assign to the underlying private attribute. Now, we can retrieve and modify the property value, as shown below.

Example: Access Property Copy
>>> s = Student('Steve')
>>> s.name 
'Steve'
>>> s.name = 'Bill'
'Bill'
```
