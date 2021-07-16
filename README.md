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

## Access Modifiers
Access modifiers is used to set the access level/visibility for classes, fields, methods and properties.
| Modifier        | Description           |
| :-------------: |-------------|
|  public      | The code is accessible for all classes |
| private      | The code is only accessible within the same class      |
| protected | The code is accessible within the same class, or in a class that is inherited from that class.      |
| internal | The code is only accessible within its own assembly, but not from another assembly.      |

## Encapsulation
The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:
- Declare fields/variables as private
- Provide public get and set methods, through properties, to access and update the value of a private field

## Why to use Encapsulation?
- Better control of class members (reduce the possibility of yourself (or others) to mess up the code)
- Fields can be made read-only (if you only use the get method), or write-only (if you only use the set method)
- Flexible: the programmer can change one part of the code without affecting other parts
- Increased security of data

## Properties
A property is like a combination of a variable and a method, and it has two methods: a get and a set method.
#### Example
```c#
class Person
{
  private string _name; // field

  public string Name   // property
  {
    get { return _name; }   // get method
    set { _name = value; }  // set method
  }
}
```

## Inheritance
In C#, it is possible to inherit fields and methods from one class to another. Inheritance concepts are divided into two categories:
- Base Class (parent) - the class being inherited from
- Derived Class (child) - the class that inherits from another class
To inherit from a class, use the : symbol.
#### Example
```c#
class Vehicle  // base class (parent) 
{
  public string brand = "Honda";  // Vehicle field
  public void Honk()             // Vehicle method 
  {                    
    Console.WriteLine("Peep, peep!");
  }
}

class Car : Vehicle  // derived class (child)
{
  public string modelName = "Civic";  // Car field
}

class Program
{
  static void Main(string[] args)
  {
    // Create a myCar object
    Car myCar = new Car();

    // Call the Honk() method (From the Vehicle class) on the myCar object
    myCar.Honk();

    // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
    Console.WriteLine(myCar.brand + " " + myCar.modelName);
  }
}
```
### Why And When To Use "Inheritance"?
It is useful for code reusability: reuse fields and methods of an existing class when you create a new class.

## Sealed keyword
If you don't want other classes to inherit from a class, use the sealed keyword
#### Example
```c#
sealed class Human 
{
  ...
}

class Person : Human 
{
  ...
}
// This will throw an error message like this: 'Person': cannot derive from sealed type 'Human'

```

## Polymorphism
Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.
Inheritance lets us inherit fields and methods from another class. Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.
And in order to implement the polymorphic behaviour, virtual keyword is added to the method inside the base class, and by using the override keyword for each derived class methods.
#### Example
```c#
class Animal  // Base class (parent) 
{
  public virtual void animalSound() 
  {
    Console.WriteLine("The animal makes a sound");
  }
}

class Cat : Animal  // Derived class (child) 
{
  public override void animalSound() 
  {
    Console.WriteLine("The cat says: meow meow");
  }
}

class Dog : Animal  // Derived class (child) 
{
  public override void animalSound() 
  {
    Console.WriteLine("The dog says: woof woof");
  }
}

class Program 
{
  static void Main(string[] args) 
  {
    Animal myAnimal = new Animal();  // Create a Animal object
    Animal myCat = new Cat();  // Create a Cat object
    Animal myDog = new Dog();  // Create a Dog object

    myAnimal.animalSound();
    myCat.animalSound();
    myDog.animalSound();
  }
}
```
```
// The output will be:
The animal makes a sound
The cat says: meow meow
The dog says: woof woof
```

## Abstract Class
Data abstraction is the process of hiding certain details and showing only essential information to the user.
Abstraction can be achieved with either abstract classes or interfaces.
The abstract keyword is used for classes and methods:
- Abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the derived class (inherited from).
An abstract class can have both abstract and regular methods:
```c#
abstract class Animal 
{
  public abstract void animalSound();
  public void sleep() 
  {
    Console.WriteLine("Zzz");
  }
}
```
From the example above, it is not possible to create an object of the Animal class:
```c#
Animal myObj = new Animal(); // Will generate an error (Cannot create an instance of the abstract class or interface 'Animal')
```
To access the abstract class, it must be inherited from another class. Let's convert the Animal class we used in the Polymorphism chapter to an abstract class.
```c#
// Abstract class
abstract class Animal
{
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep()
  {
    Console.WriteLine("Zzz");
  }
}

// Derived class (inherit from Animal)
class Cat : Animal
{
  public override void animalSound()
  {
    // The body of animalSound() is provided here
    Console.WriteLine("The cat says: meow meow");
  }
}

class Program
{
  static void Main(string[] args)
  {
    Cat myCat = new Cat(); // Create a Cat object
    myCat.animalSound();  // Call the abstract method
    myCat.sleep();  // Call the regular method
  }
}
```

## Interface
Interfaces is another way to achieve abstraction in C#
An interface is a completely "abstract class", which can only contain abstract methods and properties (with empty bodies)
It is considered good practice to start with the letter "I" at the beginning of an interface, as it makes it easier for yourself and others to remember that it is an interface and not a class.
By default, members of an interface are abstract and public. [Read more...](https://www.w3schools.com/cs/cs_interface.php)
#### Example
```c#
// interface
interface IAnimal 
{
  void AnimalSound(); // interface method (does not have a body)
  void Run(); // interface method (does not have a body)
}
```






•	Destructor: xx
•	Return Types: xx
•	This keyword: xx
•	Base Keyword: xx
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

