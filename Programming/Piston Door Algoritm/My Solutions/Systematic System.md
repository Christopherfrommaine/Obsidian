# Rough Outline 1:
- Whenever there are 0 air blocks between the topmost piston and the block to pull, then the objective is to pull the topmost piston down by one.
- Whenever there is 1 air block between the topmost piston and the block to pull, then the objective is to power the topmost piston once.
- If there are greater than or equal to 2 air blocks between the topmost piston and the block to pull, the objective is to put the piston to two blocks below the block to pull.

As pseudocode:
```
def moveBlockDown(b, state):
	moves = []
	topmostPiston = state.getTopmostPiston()
	
	match b - topmostPiston:
		case 0:
			moves += moveBlockDown(topmostPiston)
			moves += moveBlockDown(b)
		case 1:
			moves += powerPiston(topmostPiston)
		case _:
			moves += movePistonUp(topmostPiston, b - 2)
			moves += moveBlockDown(b)
	return moves

def moveBlockUp(b, state):
	moves = []
	topmostPiston = state.getTopmostPiston()
	
	match b - topmostPiston:
		case 0:
			moves += powerPiston(topmostPiston)
		case _:
			moves += movePistonUp(topmostPiston, b - 1)
			moves += moveBlockDown(b)
	return moves

def powerPiston(piston, state):
	moves = []
	
	if piston < -1:
		moves += [piston]
		return moves
	
	topmostObserver = state.getTopmostObserver(below=piston)
	topmostPiston = state.getTopmostPiston(below=piston)
	
	if topmostPiston > topmostObserver:
		# Moving pistons out of the way for observer
		moves += moveBlockDown(topmostPiston)
		moves += powerPiston(piston)
	
	if topmostObserver > topmostPiston:
		match piston - topmostObserver:
			case 0:
				while state.getTopmostObserver() != state.topAvalibleObserver().coords():
					moves += moveBlockDown(topmostObserver)
				moves += [state.avalibleObserver]
				moves += powerPiston(piston)
			case 1:
				moves += moveBlockUp(topmostObserver)
			case _:
				moves += moveBlockUp(topmostObserver)
				moves += powerPiston(piston)
```

# Problem 1: Piston Update Order
Solution: Updates from furthest to closest, unless the block being directly pushed is an observer, in which case that observer fires last.
