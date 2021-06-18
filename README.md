# About
Project from Udacity. <br>
Final project from 4th Section 
Original [GitHub project](https://github.com/udacity/P3_Implement_SLAM)

# Aproach
* TBC

# Instructions

*Below is an example of a 2D robot world with landmarks (purple x's) and the robot (a red 'o') located and found using *only* sensor and motion data collected by that robot. This is just one example for a 50x50 grid world; in your work you will likely generate a variety of these maps.*

<p align="center">
  <img src="./images/robot_world.png" width=50% height=50% />
</p>

The project will be broken up into three Python notebooks; the first two are for exploration of provided code, and a review of SLAM architectures, **only Notebook 3 and the `robot_class.py` file will be graded**:

* :white_check_mark: __Notebook 1__ : Robot Moving and Sensing
* :white_check_mark: __Notebook 2__ : Omega and Xi, Constraints 
* :white_check_mark::exclamation: __Notebook 3__ : Landmark Detection and Tracking 

## Project Rubric [link_original](https://review.udacity.com/#!/rubrics/1427/view)

### `robot_class.py`: Implementation of `sense`

#### Implement the `sense` function
| Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
| :white_check_mark: Implement the `sense` function for the robot class. |  Implement the `sense` function to complete the robot class found in the `robot_class.py` file. This implementation should account for a given amount of `measurement_noise` and the `measurement_range` of the robot. This function should return a list of values that reflect the measured distance (dx, dy) between the robot's position and any landmarks it sees. One item in the list has the format: `[landmark_index, dx, dy]`. |


### Notebook 3: Implementation of `initialize_constraints`

#### Initialize omega and xi matrices 
| Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
| :white_check_mark:   Initialize constraint matrices. |  Initialize the array `omega` and vector `xi` such that any unknown values are `0` the size of these should vary with the given `world_size`, `num_landmarks`, and time step, `N`, parameters. |


### Notebook 3: Implementation of `slam`

#### Update the constraint matrices as you read sensor measurements 
|  Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
| :white_check_mark:  Iterate through the generated `data` and update the constraints. |  The values in the constraint matrices should be affected by sensor measurements *and* these updates should account for uncertainty in sensing. |
|  :white_check_mark: Iterate through the generated `data` and update the constraints. |  The values in the constraint matrices should be affected by motion `(dx, dy)` *and* these updates should account for uncertainty in motion. |

#### `slam` returns a list of robot and landmark positions, `mu`
| Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
|  :white_check_mark:  The result of slam should be a list of robot and landmark positions, `mu`. |  The values in `mu` will be the x, y positions of the robot over time and the estimated locations of landmarks in the world. `mu` is calculated with the constraint matrices `omega^(-1)*xi`. |


#### Answer question about final pose
| Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
|  :white_check_mark:  Answer question about the final robot pose. |  Compare the `slam`-estimated and *true* final pose of the robot; answer why these values might be different. |

#### `slam` passes all tests

| Criteria       		|     Meets Specifications	        			            | 
|:---------------------:|:---------------------------------------------------------:| 
| :white_check_mark:  Test your implementation of `slam`.  |  There are two provided test_data cases, test your implementation of slam on them and see if the result matches.|

## Bonus :boom::boom::boom:
* :white_check_mark: Add visualization code that creates a more realistic-looking display world
* :white_check_mark: Display your robot world at every time step and stack these image frames to create a short video clip and to see how the robot localizes itself and builds up a model of the world over time

LICENSE: This project is licensed under the terms of the MIT license.
