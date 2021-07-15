# C# - QNA

## Class
A class is a user-defined blueprint or prototype from which objects are created.
(A class can be public or internal etc. By default, modifier of class is internal)

## Object
A instance which is created using a class is called Object. An object is basically a block of memory that has been allocated and configured according to the blueprint.

## Methods
A method is a code block that contains a series of statements. A program causes the statements to be executed by calling the method and specifying any required method arguments.

## Properties
A property is like a combination of a variable and a method, and it has two methods: a get and a set method.
### Example
```
class Person
{
  private string name; // field

  public string Name   // property
  {
    get { return name; }   // get method
    set { name = value; }  // set method
  }
}
```

•	Constructor: xx
•	Destructor: xx
•	Return Types: xx
•	Access Modifiers: xx 
•	Encapsulation: xx
•	Inheritance: xx
•	Abstract Classes: xx
•	This keyword: xx
•	Base Keyword: xx
•	Interfaces: xx
•	Polymorphism: xx
•	Sealed Class: xx
•	Static Variables: xx
•	Static Class: xx
•	Static Methods: xx

Other Stuff:
•	Entity Framework: Lambda Expressions
•	C# naming conventions
•	Generics / Data Types: <List>, Array, Dict, etc..

Inheritance:
Single Level = Parent to Child
Multi Level = Parent -> Child -> Grand Child & so on
Hierarchical = Single parent & Multiple Children
Multiple = 2 Parents & 1 child 
Hybrid = Combination of 2 inheritance

