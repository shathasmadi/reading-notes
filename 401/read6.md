# Read: 6 - Inheritance and Interfaces

## [Java OO Tutorial](https://docs.oracle.com/javase/tutorial/java/concepts/)

- I learned about:

### Inheritance

1. Object-oriented programming allows classes to inherit commonly used state and behavior from other classes.
1. In the Java programming language, each class is allowed to have one direct superclass, and each superclass has the potential for an unlimited number of subclasses
1. To create a subclass use the `extends` keyword at the beginning of your class declaration, followed by the name of the class to inherit from

### Interface

1. an interface is a group of related methods with empty bodies.
1. To implement this interface, the name of your class would change , and you'd use the `implements` keyword in the class declaration
1. If your class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.
1. To actually compile a class that uses an interface, you'll need to add the public keyword to the beginning of the implemented interface methods.

### Package

1. A package is a namespace that organizes a set of related classes and interfaces.
1. Application Programming Interface, or "API": is an enormous class library (a set of packages) suitable for use in your own applications.

## [Java Inheritance & Interfaces Tutorial](https://docs.oracle.com/javase/tutorial/java/IandI/index.html)

- I learned about:

### Interfaces

1. an interface is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types.
1. Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.
1. When an instantiable class implements an interface, it provides a method body for each of the methods declared in the interface.
1. An interface declaration consists of modifiers, the keyword interface, the interface name, a comma-separated list of parent interfaces (if any), and the interface body.
1. An interface can extend other interfaces
1. The interface body can contain abstract methods, default methods, and static methods.
1. An abstract method within an interface is followed by a semicolon, but no braces
1. Default methods are defined with the default modifier
1. static methods with the static keyword
1. All abstract, default, and static methods in an interface are implicitly public, so you can omit the public modifier.
1. All constant values defined in an interface are implicitly public, static, and final. Once again, you can omit these modifiers.

#### Using an Interface as a Type

1. If you define a reference variable whose type is an interface, any object you assign to it must be an instance of a class that implements the interface.

#### Evolving Interfaces

1. If you make a change to an interface, then all classes that implement the old interface will break because they no longer implement the old interface.
1. You could create a new interface that extends the old interface
1. Users who have classes that implement interfaces enhanced with new default or static methods do not have to modify or recompile them to accommodate the additional methods.

#### Default Methods

1. Default methods enable you to add new functionality to the interfaces of your libraries and ensure binary compatibility with code written for older versions of those interfaces.
1. To extend an interface that contains a default method, you can do the following:
   - do not mention the default method at all, which lets your extended interface inherit the default method.
   - Redeclare the default method, which makes it abstract.
   - Redefine the default method, which overrides it.
1. Integrating Default Methods into Existing Libraries

### Inheritance

1. every class is implicitly a subclass of Object.
1. inheritance is to derive your new class from the existing class.
1. The constructor of the superclass can be invoked from the subclass.
1. All Classes in the Java Platform are Descendants of Object
   - ![Hierarchy](https://docs.oracle.com/javase/tutorial/figures/java/classes-object.gif)
1. A subclass inherits all of the public and protected members of its parent, no matter what package the subclass is in. If the subclass is in the same package as its parent, it also inherits the package-private members of the parent.
1. The inherited fields can be used directly, just like any other fields.
1. You can declare a field in the subclass with the same name as the one in the superclass, thus hiding it (not recommended).
1. You can declare new fields in the subclass that are not in the superclass.
1. The inherited methods can be used directly as they are.
1. You can write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it.
1. You can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
1. You can declare new methods in the subclass that are not in the superclass.
1. You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
1. A subclass does not inherit the private members of its parent class.

#### Private Members in a Superclass

1. A nested class has access to all the private members of its enclosing class—both fields and methods. Therefore, a public or protected nested class inherited by a subclass has indirect access to all of the private members of the superclass.

#### Casting Objects

1. an object is of the data type of the class from which it was instantiated, The reverse is not necessarily
1. Casting shows the use of an object of one type in place of another type, among the objects permitted by inheritance and implementations.
1. You can make a logical test as to the type of a particular object using the instanceof operator. This can save you from a runtime error owing to an improper cast
1. You can prevent a class from being subclassed by using the final keyword in the class's declaration.
1. you can prevent a method from being overridden by subclasses by declaring it as a final method.
1. An abstract class can only be subclassed; it cannot be instantiated
