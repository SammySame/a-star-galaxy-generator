# A* Galaxy Generator
Fully playable web browser project made inside Godot Engine. <br>

**[Link to the web project](https://sammysame.github.io/a-star-galaxy-generator/)** <br>

## Gameplay
Click **REGENERATE** and move around the galaxies by left-clicking on any of them. <br>
The player “spaceship” will always spawn in the largest galaxy cluster. It will move to the selected point by picking the shortest path to it. <br>
Play around with different values for the generation. Some things worth checking out are:
<br>  - setting larger **bounding box inflate**, which will make galaxies more spread out
<br>  - changing the **amount per row** to less than 3, which will almost always make two separate clusters
<br>  - low **position randomness** will result in more evenly spaced out galaxies <br>


## Generating galaxies
[Source code for the galaxy creator](code/galaxy_view_interface.gd) <br>
At the beginning, galaxies are generated in the grid,
and then for every one of them a unique random "x" and "y" coordinate offset is applied.
To prevent the galaxies from overlapping, a bounding box test is done for each of them,
and if any overlaps are found, one of the objects is deleted.

## Generating connections
[Source code for the connector](code/galaxy_connector.gd) <br>
To create connections, a A* algorithm is used. 
Below is a demonstration of how the algorithm is utilized to create connections.
<p align="center">
  <img src="ConnectionAlgorithm.png" width="400" alt="Connection Algorith Image">
</p>
<p align="center">
  <img src="ConnectionAlgorithmExplanation.png" width="600" alt="Connection Algorith Explanation Image">
</p>
