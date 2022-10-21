---
title: "Object Oriented Programming with Java"
date: 2022-10-01T15:08:30-04:00
draft: false
---

- Back in my sophomore year I got rejected by 3 internships (or more) because my OOP skills weren't good enough. I want to make this post to remind myself I know the concepts.
---
***Java Basic Concepts***
- What is a class?
    - A class is a blueprint of anything, I mean literally anything. You can also have nested class too (this is too advanced for now). For example, a car has an engine, mpg, top speed, gear type, gear amount, and etc but the class will hold all of theses. A class holds different types of fields(states) and methods(functions).
- What is an object?
    - An object in Java are the attributes of differents types of function. For example, a car has an engine, mpg, top speed, gear type, gear amount, and etc but the class will hold all of theses. For example, there is a toyota camry, honda civic, and etc. You can use the class to make an object.
    - Note: instance and object are the same thing
- What is interface?
    - An interface is an blueprint of a class. It can only hold static constants and abstract methods. These type of methods are only used to define things but cannot hold values. For example, a car interface would consist types of methods like public float mpg, public int gearType = "" and etc.
- What is a Package?
    - A package in java is like a library in other languages. You can import a class that has functions that can write codes more efficiently. For example, `import java.util.Scanner;`, this only imports the scanner class from util library. You can also import everything from util by `import java.util.*;`
- What does static mean?
    - Static keyword means it belongs to a certain member or class type. For example, you can define a car brand like toyota in car class. They are global variables for a class. So it means you can access it without using the object compared to just declaring string make. There is static blocks, variables, methods, and classes.

***What is OOP?***

Object Orient Programming is a type of software design that is designed around objects (it's in the name).
- There are 4 main concepts
    - Encapsulation
        - This concepts will be used to hide data from other classes. So we need to have private variables and setter and getters method to access them.
        - setter will modify the variables
        - getter will get the variables
        - Then we can access the encapsulated class in another class without interfering other variables
          ```/* File name : EncapTest.java */
            public class EncapTest {
                private String name;
                private String idNum;
                private int age;
                public int getAge() {
                    return age;
                }
                public String getName() {
                    return name;
                }

                public String getIdNum() {
                    return idNum;
                }

                public void setAge( int newAge) {
                    age = newAge;
                }

                public void setName(String newName) {
                    name = newName;
                }

                public void setIdNum( String newId) {
                    idNum = newId;
                }
            }
            ```
            ```
            /* File name : RunEncap.java */
            public class RunEncap {

            public static void main(String args[]) {
                EncapTest encap = new EncapTest();
                encap.setName("James");
                encap.setAge(20);
                encap.setIdNum("12343ms");

                System.out.print("Name : " + encap.getName() + " Age : " + encap.getAge());
            }
            }
            ```
            - source https://www.tutorialspoint.com/java/java_encapsulation.htm
    - Abstraction
        - This concept is used to hide certain details and only showing essential informations
        - An abstract class is a restricted class that can used to create objects, must be interited
        - An abstract method can only be used in abstract class and it does not have a body
            ```
            // Abstract class
            abstract class Animal {
                // Abstract method (does not have a body)
                public abstract void animalSound();
                    // Regular method
                    public void sleep() {
                        System.out.println("Zzz");
                    }
            }

            // Subclass (inherit from Animal)
            class Pig extends Animal {
                public void animalSound() {
                    // The body of animalSound() is provided here
                    System.out.println("The pig says: wee wee");
                }
            }

            class Main {
                public static void main(String[] args) {
                    Pig myPig = new Pig(); // Create a Pig object
                    myPig.animalSound();
                    myPig.sleep();
                }
            }
            ```
            - source https://www.w3schools.com/java/java_abstract.asp
            - We can see above animal class is getting inherited by pig class. Then we see the abstract method has no body.
            - Abstraction is used to generalize things, for example there are many types of animal. All animals has color, age, and etc
    - Inheritance
        - This concept is to inherit another class's attributes and methods 
        - A subclass is a child and it inherits from another class
        - A superclass is a parent and is being inherited to another class (e.g. abstract class)
        - 
            ```
            class Vehicle {
                protected String brand = "Ford";        // Vehicle attribute
                public void honk() {                    // Vehicle method
                    System.out.println("Tuut, tuut!");
                }
            }

            class Car extends Vehicle {
                private String modelName = "Mustang";    // Car attribute
                public static void main(String[] args) {

                    // Create a myCar object
                    Car myCar = new Car();

                    // Call the honk() method (from the Vehicle class) on the myCar object
                    myCar.honk();

                    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
                    System.out.println(myCar.brand + " " + myCar.modelName);
                }
            }
            ```
        - source https://www.w3schools.com/java/java_inheritance.asp
        - As we can see above, Vehicle is the superclass and the Car is a subclass. Using the `extends` keyword will inherit the class. We can also use the honk method and the brand variable from vehicle since it is inherited.

    - Polymorphism
        - This is probably the hardest concept for me to wrap around, remember failing this interview so hard.
        - This concept is used to create many form. For example, an animal can be a dog, a cat or other animals.
        ```
        class Animal {
            public void animalSound() {
                System.out.println("The animal makes a sound");
            }
        }

        class Pig extends Animal {
            public void animalSound() {
                System.out.println("The pig says: wee wee");
            }
        }

        class Dog extends Animal {
            public void animalSound() {
                System.out.println("The dog says: bow wow");
            }
        }

        class Main {
            public static void main(String[] args) {
                Animal myAnimal = new Animal();  // Create a Animal object
                Animal myPig = new Pig();  // Create a Pig object
                Animal myDog = new Dog();  // Create a Dog object
                myAnimal.animalSound();
                myPig.animalSound();
                myDog.animalSound();
            }
        }
        ```
        - source https://www.w3schools.com/java/java_polymorphism.asp
        - As we can see above Animal class can be a pig or a dog or a myanimal. It can be many forms, they are all come from the same class. 
    - Bonus!!!!!
        - Two more concepts that are extremely important, overloading and overriding in methods
        - Overloading is having two methods of the same name but different arguments
        ```            
            class MethodOverloadingEx {    
                static int add(int a, int b)
                {
                    return a + b;
                }

                static int add(int a, int b, int c)
                {
                    return a + b + c;
                }
            
                public static void main(String args[])
                {
                    System.out.println("add() with 2 parameters");
                    System.out.println(add(4, 6));
                
                    System.out.println("add() with 3 parameters");
                    System.out.println(add(4, 6, 7));
                }
            }
        ```
        - Overriding is overrides a class method from another class. This means it can the method from superclass in the subclass. Overriding is very common in polymorphism like above.
        ```
        class Animal {
            void eat()
            {
                System.out.println("eat() method of base class");
                System.out.println("eating.");
            }
        }
        
        class Dog extends Animal {
            void eat()
            {
                System.out.println("eat() method of derived class");
                System.out.println("Dog is eating.");
            }
        }
        
        class MethodOverridingEx {
            public static void main(String args[])
            {
                Dog d1 = new Dog();
                Animal a1 = new Animal();
        
                d1.eat();
                a1.eat();
        
                Animal animal = new Dog();
                // eat() method of animal class is overridden by
                // base class eat()
                animal.eat();
            }
        }
        ```
        - source https://www.geeksforgeeks.org/difference-between-method-overloading-and-method-overriding-in-java/
***Pros and Cons of OOP*** 
- Pros
    - You can build programs that are modular based and structured
    - Very enterprise friendly like Java (Jobs!!!!)
    - Everything is an object
    - Low development cost
    - I heard it's more secure?
- Cons
    - A lot of boilerplate code
    - Desigining good OOP structure can be hard, and might shoot yourself in the foot sometimes
    - Can be slow sometimes
    - Code can get messy
    - Everything is an object
