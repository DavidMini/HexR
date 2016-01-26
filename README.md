# HexR
A project I made on my own time throughout 2015. I utilized Java and the LibGDX framework to create a fun and challenging phone puzzle game. Everything you see was created by me but I did recieve some help from friends with some of the textures. 

The game was originally intended to be cross platform but due to time and developer fees I have decided to just release for Android. If you wish to look at the game files the base content will be found in core and assets can be found in android. The game cannot be found in the android store just yet but I plan to touch up the code and finaly release it. Everything in the game works right now except for leaderboards.

##Screenshots and Gifs of Gameplay:

These will be added soon...

#Highlights of the Project

##Scalability:

HexR is an android application and therefor it must be scalable to different devices. The entire game has been made with every phone screen in mind; so practically every collision detection and element in the game utilizes dynamic sizes. For this reason HexR should be able to work just fine on any device and the limited use of new apis allow it to scale back all the way to Android 2.1.

##Leaderboards:

This is the final feature that I wish to implement into the game. This is close to completion but due to LibGdx being slightly outdated there are a lot of system errors that I need to work around. I actually paused development on this project because of this but plan to fix this and release it sometime in the first half of 2016.

##Hexagon Grid Algorithm

This was actually quite a challenge to complete so I decided to include it. The game generates a grid assigns an index to each hex (x, y) where x represents the row index and y represents the column index. Since the game requires the user to place shapes and pop lines I figured there must be some sort of pattern relating lines (a combination of indexes) to the index from a hex placed on the grid. I started with using a single hexagon and after rigirous plotting with different sample peices I was able to come up with a general mathematical forumala. The formula returns the start and end indixes of a line (essentialy two other hexagons on the grid that when connected form a line) based on a given start index (that would be the index from the hexagon that was placed). This was then simply scaled to each hexagon in a shape and used for each possible line at a given position (based on the grid there are 3 lines from any point on the grid). This not only saves a lot of running time, but also dramatically reduced the performance levels of the game which initially used recurssion to determine which lines need to be checked. 

##Dynamic Menu System

The menu system is meant to blend in great visual design and user interfacing. Every screen is made with the centralal hexagon grid in mind and the game changes the user interface based on what is needed to be shown. For example the trophy tab uses each hex in the grid as a clickable trophy and the skin tab uses the hexagons to demonstrate the graphical skin change. The menu uses in game elements, which I have created, and it breaks away from using conventional forms and lists.

#GameState and Trophy Reading/Loading

Since the game is endless it makes sense to be able to return to where you previously left off. HexR uses basic file reading and writing to save the state of the board along with any progress you might have with trophies (ones you unlocked and/or currently are completing). This gives the user incentive to come back and try to beat their highscores and continue unlocking content for the game.
