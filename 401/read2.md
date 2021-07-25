# Read: Class 02 Arrays, Loops, Imports

## [Packages and Import](https://perso.ensta-paris.fr/~diam/java/online/notes-java/language/10basics/import.html)

- I learned about:

1. a package is the same as directory
1. package declarations must be the first statements
1. after importing a package you can specify classes from that package
1. For small programs it's common to omit package declaration, although it is not recommended.
1. The wildcard character (\*) is used to specify that all classes with that package are available to your program.
1. you can specify the exact class that you want to use instead of \*
1. Common imports:
   - import java.awt.\*; Common GUI elements.
   - import java.awt.event.\*; The most common GUI event listeners.
   - import javax.swing.\*; More common GUI elements. Note "javax".
   - import java.util.\*; Data structures (Collections), time, Scanner, etc classes.
   - import java.io.\*; Input-output classes.
   - import java.text.\*; Some formatting classes.
   - import java.util.regex.\*; Regular expression classes.
1. imports doesn't make the file larger
1. using \* in the import prevents accidentally defining classes with names that conflict with the standard library names
1. import with \* doesn't include any of the subpackages
1. Static imports in Java 5 leads to name pollution and confusion about which class constants come from.

## [A Guide to Java Loops](https://www.baeldung.com/java-loops)

- I learned about:

1. the types of loops that we can find in Java:
   - Simple for loop: incrementing and evaluating a loop counter.
   - Enhanced for-each loop: for each element
   - While loop: while a condition is true
   - Do-While loop: the first condition evaluation happens after the first iteration of the loop.
