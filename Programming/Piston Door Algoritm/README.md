This is the documentation to build an algorithm which can generate the sequences of steps needed to move pistons in a piston door. It is best viewed in Obsidian (the writing software), so if you want nice formatting and embedded visuals in this document, you should download that.

I've tried to create this algorithm before, but I could not get it to work: https://github.com/Christopherfrommaine/autoPistonDoor/tree/master/Algorithm

# Instructions

- when given
	- an initial y-coordinate of a block (with respect to the floor level)
	- a final y-coordinate of a block
- and when you can assume that the initial conditions are
	- a set of pistons in the normal state
		- all the pistons are present and are as far down as possible
		- all the observers are present
	- no blocks are present below the given initial y-coordinate
- design an algorithm that can find a sequence of inputs which move the block from the initial position to the final position.

Examples of such an output are given in the example code document, with pictures and videos to go along with it to understand the process

There are a few other steps that must go into creating the final code for the piston door, such as storing and moving around blocks, but these are minimal and can be done fairly easily by hand, so you don't need to worry about them.

# Notes on Minecraft Mechanics

For inputs 15, 14, 13, and 12, note that there is quasiconnectivity, which means that two pistons are fired at once: the one the observer is pointed into, and the one below. This may need some consideration, though it's probably pretty easy to get around (i.e., wherever you put a 13, replace it with the sequence 13, 14, 15).

Pistons have a maximum push limit of 12 blocks. This occurs rarely enough that I don't think it's a major issue if you don't include this in your program.

When extending, pistons are immovable. This shouldn't come up almost at all, except for scenarios like described in the following issue.

When a section containing multiple pistons and observers is pushed, I don't know how the piston that fires first is determined (e.g., if you have POPOP and you have the leftmost piston push the others, I don't know whether the rightmost piston will fire, or the middle piston will fire which will then cause the rightmost piston to fire). It is repeatable, but I don't know if it can be determined without closer examination into how minecraft pistons work. This problem could also be solved by hand, as it should be rare enough to merit special treatment.

# World Download

A world download is provided, so that you can see the rest of the piston layout for yourself. You need not worry about most of the redstone, but note that there are signs on most of the observers which indicate what input goes to them.

There is a control platform at coordinates (-20, 86, -40).
To reset the piston door to it's normal state (unless you've messed it up a lot), press the big red button.
To load the preset program I have already written by hand with composters, press the wooden button that says 'all', which loads all the segments of memory to be played through (the stone buttons can select a specific portion of memory to play through, but this is for more advanced use).
To run the door, press 'continual'. To run it only for one movement, press 'single'.
Make sure that the 'Auto-Override Signal Strength' light is always on.

TLDR:
To reset and run, press the big red button, wait for the commands to stop, press 'all', then press continual.

# Memory in the World Download

The memory is stored in composters starting at coordinates (-103, 55, -76) and read from north to south, from east to west. So, facing east and downwards, it is read like a sheet of paper.

Each instruction is loaded in two composters, with the left (facing east) holding the more significant digit.
Each number is stored in base seven with every digit added to by 1. So to encode 15, you get 21 in base 7, which is turned into 32 when you add 1 to each digit, and so you fill two consecutive composters with 3, then 2 fill levels. (A tip: a pumpkin pie always gives exactly one fill level if you ever plan to do this by hand.)

I made a program to do this automatically, but I cant seem to find it. If you actually get far enough where you can't test it by hand anymore, let me know and I can find it.
