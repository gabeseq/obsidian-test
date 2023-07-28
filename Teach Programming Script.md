# Overview

## Java Basics
Welcome to Controls
We program in **JAVA**

### Variables
The most basic unit of programming is a *variable*, which is something that lets us store information.
Variables come in a few basic types:
- Integer - `int`
- Decimal Number - `double`
- True/False value, or "Boolean" value - `boolean`

In the below snippet, `x` is a variable of type `int` which we are assigning a value of 5:
```java
int x = 5;
```

### Classes
A *Class* is like a blueprint for defining a collection of data to represent a real-world object, typically a piece of hardware on the robot.

Classes can have *member variables*, which are variables that belong to that class. For example, the `Robot` class might have a variable called `drivetrain` which represents the chassis and drivetrain motors of the robot.

Classes also have *methods*, which are functions specific to that class. They typically operate
### Objects
Classes are just templates, though. To use the Class, we need to create an *instance* of it. For Objects this is done with the keyword `new`. For example,
```java
private CANSparkMax my_motor = new CANSparkMax();
```
In this example, we're storing an instance of the CAN Spark Max inside a variable name called `my_motor`. This 