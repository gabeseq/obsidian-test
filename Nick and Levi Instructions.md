- setup two master motors for left and right - these should be WPI_TalonSRX or standard CANSparkMax
- invert the right side motor
- setup followers (slaves) for each side
- Create a DifferentialDrive object within the robot, passing in the master motors for each side
- Create a drive method that takes two parameters: speed and rotation
- There's a DifferentialDrive method called `drive()` or something that takes these two parameters. use it in that method


-------


- create a default command for your drivetrain subsystem in RobotContainer: i.e. Subsystem.setDefaultCommand(new RunCommand(() -> subsystem.drive());
- pass the left Y axis into the speed parameter, and the right X axis into the rotation parameter
- have a nice cuppa tea

progr