# C# - QNA

## Class
A class is a user-defined blueprint or prototype from which objects are created.
(A class can be public or internal etc. By default, modifier of class is internal)
#### Example
```c#
class Car 
{
  string color = "red";
}
```

## Object
A instance which is created using a class is called Object. An object is basically a block of memory that has been allocated and configured according to the blueprint.
#### Example
```c#
Car honda = new Car();
```

## Class Members
Fields and methods inside classes are often referred to as "Class Members"

## Field/Variable
When a variable is declared directly in a class, it is often referred to as a field (or attribute).
#### Example
```c#
public Class Car
{
  string color = "red";
  private DateTime _date;
  public string Day = "Monday";
  
}
```

## Method
A method is a code block that contains a series of statements. A program causes the statements to be executed by calling the method and specifying any required method arguments.
#### Example
```c#
class Program
{
  static void MyMethod() 
  {
    // code to be executed
    Console.WriteLine("This is a test");
  }
}
```

## Method Overloading
In C# with method overloading, multiple methods can have the same name with different parameters:
#### Example
```c#
static int Add2Nums(int x, int y)
{
  return x + y;
}

static double Add2Nums(double x, double y)
{
  return x + y;
}
```

## Properties
A property is like a combination of a variable and a method, and it has two methods: a get and a set method.
#### Example
```c#
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
## Constructor
A constructor is a special method that is used to initialize objects. The advantage of a constructor, is that it is called when an object of a class is created. It can be used to set initial values for fields
#### Example
```c#
// Create a Person class
class Person
{
  public string name;  // Create a field

  // Create a class constructor for the Person class
  public Person()
  {
    Name = "John"; // Sets the initial value for name
  }
  
  // Create a class constructor with parameter // This is also an example of constructor overloading
  public Person(string name)
  {
    Name = name; 
  }

  static void Main(string[] args)
  {
    Person John = new Person();  // Create an object of the Person Class (this will call the constructor)
    Console.WriteLine(John.model);  // Print the value of model
  }
}

// Outputs: John
```

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

