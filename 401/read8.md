# Read: Class 08 Read: 08 - OO Design

## [SOLID principles intro](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

- I learned about:

### five object-oriented design (OOD) principles

1. Single-responsibility Principle
1. Open-closed Principle
1. Liskov Substitution Principle
1. Interface Segregation Principle
1. Dependency Inversion Principle

### Single-Responsibility Principle

1. A class should have one and only one reason to change, meaning that a class should have only one job.

### Open-Closed Principle

1. Objects or entities should be open for extension but closed for modification.

### Liskov Substitution Principle

1. Let q(x) be a property provable about objects of x of type T. Then q(y) should be provable for objects y of type S where S is a subtype of T.
   This means that every subclass or derived class should be substitutable for their base or parent class.

### Interface Segregation Principle

1. A client should never be forced to implement an interface that it doesn’t use, or clients shouldn’t be forced to depend on methods they do not use.

### Dependency Inversion Principle

1. Entities must depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

## [OO SOLID principles in real life](https://dzone.com/articles/the-solid-principles-in-real-life)

- I learned about:

1. the code that follows SOLID principles is code that's a lot more likely to be maintainable

### s is for single responsibility principle

1. the single responsibility principle (srp) asserts that a class or module should do one thing only.
   - Real life example:
     in your day to day life, picture those "duck" vehicles you see occasionally in some lakeside towns. they're street legal and water-capable, so a duck tour affords you the unique and surreal experience of being in a 'car' that gets to the edge of the water and just keeps going. fun, right?
     and yet, you don't see a whole lot of them because no one wants to be unable to drive to work because their boat rudder is broken.

### o is for open/closed principle

1. the open/closed principle states that code entities should be open for extension, but closed for modification, you should write a class that does what it needs to flawlessly and not assuming that people should come in and change it later.
   - Real life example:
     all smartphones have app stores and these app stores let you extend the base functionality of the phone which is closed for modification and they open it to an extension.

### l is for liskov substitution principle

1. is the one here that is most unique to object-oriented programming. the lsp says, basically, that any child type of a parent type should be able to stand in for that parent without things blowing up.
   - Real life example:
     to picture this, imagine cooking yourself a stew. if you're anything like me, you'd only put things in there that were edible because you would want to eat the stew without picking through each bite, asking yourself repeatedly, "is this edible?"

### i is for interface segregation principle

1. you should favor many, smaller, client-specific interfaces over one larger, more monolithic interface. in short, you don't want to force clients to depend on things they don't actually need.
   - Real life example:
     to picture this in the real world, think of going down to your local corner restaurant and checking out the menu. you'll see all of the normal menu mainstays, and then something that's just called "soup of the day." why do they do this? because the soup changes a lot and there's no sense reprinting the menus every day.

### d is for dependency inversion

1. write code that depends upon abstractions rather than upon concrete details.
   - Real life example:
     to visualize this in your day to day, go down to your local store and pay for something with a credit card. the clerk doesn't examine your card and get out the "visa machine" after seeing that your card is a visa. he just takes your card, whatever it is, and swipes it. both you and the clerk depend on the credit card abstraction without worrying about specifics.
