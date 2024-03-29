# Overview

## Java Basics
Welcome to Controls
We program in **JAVA**

### Variables
The most basic element of programming is a *variable*, which is something that lets us store information.
Variables come in a few basic types:
- Integer, e.g. **==5==** - `int`
- Decimal Number, e.g. **==0.25==** - `double`
- True/False value, or "Boolean" value - `boolean`

In the below snippet, `x` is a variable of type `int` which we are assigning a value of `5`:
```java
int x = 5;
```
You will notice that this line ends with a semicolon. In Java, all statements must end with a semicolon, and most single lines of Java you write will be statements.
### Functions
A function is a block of code which executes a given set of steps. This is useful when you have common operations that you might want to do on a regular basis.

```java
private void sayHello()
{
System.out.println("Hello!");
}
```
This function prints out "Hello!" to the console whenever it is invoked. You would do so by writing the line `sayHello();`
```java
private int add(int a, int b)
{
	return (a + b);
}

int sum = add(5, 1);
```
In this code snippet, we've declared a function called `add` which takes two *arguments*, `a` and `b`. An argument lets you pass data into a function for it to use in its operation. In this case, the function adds together the two integers we supply as arguments and returns another integer that is the sum of those arguments. The value in the `return` statement must be of the same type as the function declaration, which we declared to be `int`.

### Classes
A *Class* is like a blueprint for defining a collection of data to represent a real-world object, typically a piece of hardware on the robot.

Classes can have *member variables*, which are variables that belong to that class. For example, the `Robot` class might have a variable called `drivetrain` which represents the chassis and drivetrain motors of the robot.

Classes also have *methods*, which are functions specific to that class. They typically operate on data stored in objects and variables which belong to that Class.
### Objects
Classes are just templates, though. To use the Class, we need to create an *instance* of it. For Objects this is done with the keyword `new`. This invokes that Class's **Constructor**, which looks sort of like a method but is the name of the object. Many constructors have required parameters in order to create a new instance of that object. For example,
```java
private CANSparkMax my_motor = new CANSparkMax(port, type);
```
In this example, we're calling the constructor of the class CANSparkMax, which requires a port, or CAN ID, and a type, either brushed or brushless. Then we're storing an instance of the CAN Spark Max inside a variable name called `my_motor`. This variable represents an Object which is an instance of the Class called `CANSparkMax` and gives us access to its methods.

### Logic 
Sometimes you want your program to execute different steps based on the state of some value or function. The most basic way to do this is with an `if` statement. The general syntax is 
```
if (condition)
{
	do some stuff;
}
```
where your condition is any expression which can  be evaluated to a Boolean value of either `true` or `false`.
```java
//NOTE: the == sign evaluates whether the items on either side are equal

if (name == "Gary")
{
System.out.println("Hi Gary!");
} else
{
System.out.println("WHO ARE YOU?");
}
```

## WPILib
For FRC, the main library which we use to program robots is called WPILib. This provides helpful Classes and methods for controlling nearly every FRC-legal component that you can put on a robot.

### Subsystems
In the architecture of our robot we separate Subsystems into their own Classes, which themselves are extensions of the WPILib `SubsystemBase` class. Each subsystem is a collection of any motors, servos, solenoids, sensors, data, etc. that pertain to the operation of a specific robot subsystem, such as a shooter, climber, elevator, etc.

### Commands
We use the Command-Based framework available in WPILib to control our robot.
Think of Commands as special methods which can be passed to a higher-level scheduler that ensure that each Subsystem on the robot is not doing more than one thing at a time.
Creating commands looks like this
```java
// Spin the motor at the set speed
private void spinMotor()
{
	my_motor.set(my_speed);
}

// Command to spin the motor
public Command spinMotorCommand()
{
	return run(() -> spinMotor());
}
```
This method would live inside of a Subsystem class and would return a Command which executes the `spinMotor()` function, which itself calls the set method from the motor object, which is used to set the speed.

### Xbox Controller
We drive and control the robot with Xbox controllers, and WPILib has a handy-dandy class to make it easier to use called `CommandXboxController`

A controller is created like this:
```java
private static final int port = 0;
CommandXboxController driverController = new CommandXboxController(port);
```
where the `port` is whichever USB port is detected by the FRC Driver Station software, typically the first controller you plug in will be port 0.

Then you use the controller to invoke your subsystem commands, like this:
```java
driverController.a().onTrue(mySubsystem.spinMotorCommand());
```

### Vendor Dependencies
REVLib Link: - https://tinyurl.com/revlib