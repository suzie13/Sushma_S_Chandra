---
layout: project
project_title: "YOUBOT MANIPULATION"
project_caption: "One-liner description | Sept 2022."

project_content:
    - 
        type: image
        title: A caption for the above image.
        body: /assets/images/fulls/01.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        title: "Overview"
        body: "Control Youbot Mobile Robot to pick a cube from any specified position and place it at a goal position.
        
        <br/>
        <br/>

        The configuration variables are:
        <br/>
        q = [x_box, y_box, θ_box, x_jack, y_jack, θ_jack]
        "
    
    -
        type: paragraph
        title: "Skills"
        body: "
        <ul>
            <li>Python</li>
            <li>Robotic Manipulation</li>
            <li>CoppeliaSim</li>
        </ul>
    
    -
        type: paragraph
        title: "Description"
        body: "
        <strong>
        <i>
        To create the complete trajectory for end-effector the task is divided into 8 steps for 8 separate trajectories:
        </i>
        </strong>

        <ul>
            <li>In the first step (traj1), to move the end-effector from its initial start position to the block but with a standoff 
            i.e. at a certain z height above the cube, a screw trajectory is incorporated. </li>
            <li>In the second step (traj2), to move the end-effector from the standoff position above the initial cube position 
            to the position where the end-effector can grasp the cube, a cartesian trajectory is incorporated so that it can move in a straight line.</li>
            <li>•	In the third step (traj3), the end-effector position remains the same though in that period the gripper position is changed from 
            open to closed, cartesian trajectory is incorporated. </li>
        </ul>

        <strong>
        <i>
        For calculating the Feedback Control:        
        </i>
        </strong>
    
        "

    - 
        type: image
        body: /assets/images/fulls/01.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
    type: paragraph
    body: "
    PI control was used that made the motion smooth. 
    For the new task:
    Kp = 18 and Ki = 11 
    The X_error plot is shown below:
    "

    - 
        type: image
        body: /assets/images/fulls/01.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -

---
