# Polymorphism & Composition Homework - Quiz

# Polymorphism

1. What does the ___word___ 'polymorphism' mean?
The term polymorphism comes from two Greek words: 'poly' meaning 'many' and "morph" meaning 'change'. When we talk of something being 'polymorphic' we mean that it can have 'many forms'

2. What does it mean when we apply polymorphism to OO design? Give a simple Java example.

In object-oriented programming, polymorphism refers to a programming language's ability to process objects differently depending on their data type or class. An example could be using an interface to instead of the individual classes to input objects into an array. 


3. What can we use to implement polymorphism in Java?
Polymorphism can be implemented using both abstract classes and interfaces. Remember that all classes which inherit from a class can take the type of the superclass. To use an abstract class we create a superclass which all the classes we want to treat as being the same can inherit from. But, inheritance is fraught with problems and we can quickly get into a mess. We can also just have one superclass.
Interfaces also allow us to treat a class as being of another type. When a class implements an interface it gains the type of the interface without having a horrible inheritance chain. We can have as many interfaces as we like, too. Rather than just one super class

4. How many 'forms' can an object take when using polymorphism?

Unlimited

5. Give an example of when you could use polymorphism.

An example could be using an interface to instead of the individual classes to input objects into an array. See below where both Desktop and Printer classes are needed:

public class Network {
    private String name;
    private ArrayList<Desktop> devicesDesktop;  //DELETED
    private ArrayList<Printer> devicesPrinter;

    public Network(String name){
        this.devicesDesktop = new ArrayList<Desktop>(); //DELETED LINE
        this.devicesPrinter = new ArrayList<Printer>();
        this.name = name;
    }

See below where interface called IConnect is used in there place:

  private ArrayList<IConnect> devices;  //UPDATED

    public Network(String name){
        this.devices = new ArrayList<IConnect>();  //UPDATED
        this.name = name;
    }

This sort of use makes the code easy to expand.




# Composition

6. What do we mean by 'composition' in reference to object-oriented programming?

Composition refers to a has-a relationship where an object is made up of one or more other objects.

7. When would you use composition? Provide a simple example in Java.

If we wanted the computer to output data using a printer or a speaker, or anything that outputs data. We want a common set of abilities that our things can do without polluting their class hierarchy which things that don't concern it.

More than that, we don't want this thing to have any clue about that behaviour, just to make sure that it exists on our object. A printer NEEDS to output data, a monitor NEEDS to output data but we don't want our structure to care HOW they output data.



8. What is/are the advantage(s) of using composition?

Composition allows a class to use behaviour from a group of other classes, and makes it possible for that behaviour to change at runtime.

9. When an object is destroyed, what happens to all the objects it is composed of?

When the object is destroyed all of its behaviours are also destroyed.