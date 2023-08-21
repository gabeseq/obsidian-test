# TELL
## Sample Project
- Basic Syntax
- Objects
- Variables
- Logic Flow
- Methods
- Motors/Servos/"Components"
- Subsystem method
- Commands
- XBox Controller

# DO
## MVP (Minimum Viable Product)
Start with EMPTY CommandRobot Project
In ExampleSubsystem:
- [ ] Create a Motor
- [ ] Create Method to spin
- [ ] Create Command to run `spin()` method
- [ ] Map XBox button to the Command

## Advanced
- [ ] Use feedback from Encoder
- [ ] Use Multiple buttons for different functions
	- e.g. A toggles SpinCommand, B reverses direction, X stops while held, Y spins 5 rotations then stops
- [ ] More control methods to support the functionality of the additional buttons
	- `spinVBus(vbus)`
	- `spinRevs(numRevs)`
	- `toggleSpin()`


Lesson Plan:
Tell:
• Object—A piece of hardware (ex. motor controller, solenoid, servo, controller, etc.)
• Variable—A piece of stored information (ex. Integer (int), Decimal (double), Word (String),
Object)
• Logic Flow:
o Methods—Perform an action, such as setting a motor’s speed.
▪ Parameter—A variable for the method.
o Commands—Call a method, can be called by an Xbox button.
o Button bindings—When I press <Button>, <Command> happens.
• Syntax:
o Semicolons at the ends of lines.
o Scope resolution operator = period
o
Do:
MVP:
• Ctrl + Shift + P -> WPILib: Create a new project.
• Settings (Language: Java, Name: Something, Team Number: 4028, etc.)
• Navigate to ExampleSubsystem.java
• Declare motor (ex. CANSparkMax m_motor)
• Initialize motor in constructor.
• Make new method that takes in a double “speed” param.
• Motor.set(speed);
• Make a command that calls the method.
• Navigate to RobotContainer.configureButtonBindings()
• Reference the button with m_driverController.<button>().onTrue();
• Pass in the previously created command
(m_driverController.<button>().onTrue(ExampleSubsystem.<command>(<parameter>)))
• Lamba
Advanced:
• Declare encoder (ex. RelativeEncoder m_encoder)
• Initialize the encoder with m_motor.getEncoder();
• Create a new command method that uses the set method in the factory run() method along with
command decorators to use encoder feedback to rotate to a specific position.
o Store getEncoder() into a variable in a runOnce() with an andThen() decorator at the end
to run the run().
o Run motor.set() in the run() method
o Use the .until() decorator to limit the encoder position to the relativePosition + the
desired amount of rots.
• Bind this new command to a new button in RobotContainer.configureButtonBindings()
Level 2:
• Casing best practices
o camelCase for variables
o CAPITAL_SNAKE_CASE for constants.
o TitleCase for Classes + Enums
• Formatting/Organization
• Enums + State Machines
• Subsystem Planning
o Be Extensible!
• Basic PID – position control
• Stringing Commands together
o Parallel & Sequential Groups
o Multi-Subsystem Commands
• Current Limiting & Sensing
• Phoenix Tuner, REV HW Client
• RoboRIO Imaging & Maintenance
Remember: git
Level 3:
• Advanced PID
o Tuning
o Velocity
o Motion Magic & NO bad
o Profiled PID
• Robot Architecture
• Conditional & State-Sensitive Commands
• SysID & Feedforward
• Accessing External Data
o Coprocessors
o NT – LL, PV
o Color Sensor
o TOF sensor
Level weee:
• Coprocessors
• Interfaces & Abstract Classes
• Rust ()