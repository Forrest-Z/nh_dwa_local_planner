# nh_dwa_local_planner
Contains a modified Dynamic Window Approach(DWA) local planner for car like and
4WS robots.  

#### Changes:
Two new cost functions were added:
- **fws_cost_function** allows only nonholonomic trajectories for car  
like robots, as well as parallel motions(crab steering) for 4WS robots, if  
selected. The cost function uses two new parameters:  
  1. *r_min*: minimum turning radius  (>0 for car like and 4WS robots)  
  2. *b_max*: maximum sideslip angle  (>0 for 4WS robots)  

- **goal_orientation_cost_function** is enabled close to the final goal and its  
purpose is to reward the trajectories that achieve the lowest orientation error,  
and at the same time the lowest distance from the final goal.  
This cost function uses three new parameters:
  1. *activation_factor*: the higher the activation factor, the lower the  
  distance from the final goal that activates this cost function
  2. *orientation_scale*: scales the cost of orientation error
  3. *distance_scale*: scales the cost of distance from the final goal error
