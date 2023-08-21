# Instructions
1. Create a new Java project with the CommandRobot template
2. Expand the folder `src/main/java/frc/robot/subsystems/`
3. In the ExampleSubsystem, create a CANSparkMax called motor below the line that says
```java
public class ExampleSubsystem {
```
4. Below the line
```java
public ExampleSubsystem() {
```
Initialize the motor by setting motor equal to `new CANSparkMax(4, MotorType.kBrushed);`
5. Below the next '}', declare a new method
6. TBD