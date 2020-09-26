# Cellular Automata MatNumba
Cellular Automation using the same numerical computation from the original Cellular_Automata_Pyglet repo, but the graphical representation is done using Matplotlib and savefig function for more flexibility, simpler code, and better performance. Numba is also implemented in numerical_grid file 

#### There are two main files:
- numerical_grid.py
- graphical_grid.py

- 'Examples' includes a videos of Conway's Game of Life and Accumulation. (For Generating Videos go to subheading 'FFMPEG')

numerical_grid generates a square matrix of 1s and 0s and returns it to graphical_grid. The arrangement of 1s and 0s is determined by the methods used inside numerical_grid.py.

Once the grid is generated it is passed to graphical_grid.py. The graphical_grid.py uses matplotlib library to generate graphical representation of the matrix.
Here, 1 is represented by a white cell and 0 by black. The grid is again passed into the numerical_grid functions to be updated for the next iteration.
The whole process is repeated under a definite for loop.

### Other methods
By default, all functions return values so that the end result is to represent Conway's Game Of Life. The default methods are specified in the default_parameters.txt file. These methods can be changed to generate different Cellular Automata models as instructed in numerical_grid.py

under numerical_grid.py are 3 main functions:
 1) `first_numerical_grid()`
 2) `sum33()`
 3) `rules()`

`first_numerical_grid()` acts as an initial condition (or initial grid layout of 1s and 0s). The very first grid that is generated by default is a random arrangement of 1s and 0s. This can be changed by either using one of the other initail condition methods inside this `first_numerical_grid()`, or you can introduce your own method.

`sum33()` includes different ways to take the sum of a 3x3 matrix within the larger matrix generated by `first_numerical_grid` or from later iterations.

`rules()` determines how the central cell should behave (whether be 1 or 0) based on the summed value obtained from `sum33()`

### FFMPEG
Since the graphical_grid.py generates an image sequence of .png files for each frame. These images can be used to create a video file using ffmpeg, the `code ffmpeg.txt` file is provided with the code that can be used through command line (cmd) to generate a video file.


### Why Use Matplotlib?
The benefits of using matplotlib in this case is mostly subjective but nevertheless needs to be mentioned:
1) Better performance: since the program doesn't need generate cells one square at a time.
2) The code is much simpler and smaller.
3) Since the program can generate each frame, it provides enough flexibility to keep the data of any frame and continue from there later on. In other words, the simulation can start(or continue) from the frame generated in the last session.
  e.g I can create a simulation from iteration 0-100 at one time, I can continue from 100-200 at someother time, given that I saved the data from the last frame from my previous session.
4) The image quality of each frame can also be changed inside the matplotlib's `plt.savefig` function. 
  
  
### Sample Video (Game Of Life):
[![Video](http://img.youtube.com/vi/5nV34VjGowg/0.jpg)](http://www.youtube.com/watch?v=5nV34VjGowg "Video Link [Game Of Life]")


### Sample Video (Different Rules):
[![Video](http://img.youtube.com/vi/ShfjuoqGClM/0.jpg)](https://www.youtube.com/watch?v=ShfjuoqGClM "Video Link [Different Rules]")

Description:
- 500x500 cells
- 30 frames per second
- Initial Grid = Random
- Rules = Game Of Life
