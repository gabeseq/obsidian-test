# TELL
## Sample Project
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


