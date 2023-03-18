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
        
        <br>
        <br>

        <b>Skills</b>

        <ul>
            <li>Python</li>
            <li>Robotic Manipulation</li>
            <li>CoppeliaSim</li>
        </ul>
        <br>
        <br>
        "
    -

        type: paragraph
        title: "Description"
        body: "
        <b>
        <i>
        To create the complete trajectory for end-effector the task is divided into 8 steps for 8 separate trajectories
        </i>
        </b>

        <ul>
            <li>In the first step (traj1), to move the end-effector from its initial start position to the block but with a standoff 
            i.e. at a certain z height above the cube, a screw trajectory is incorporated. </li>
            <li>In the second step (traj2), to move the end-effector from the standoff position above the initial cube position 
            to the position where the end-effector can grasp the cube, a cartesian trajectory is incorporated so that it can move in a straight line.</li>
            <li>In the third step (traj3), the end-effector position remains the same though in that period the gripper position is changed from 
            open to closed, cartesian trajectory is incorporated. </li>
            <li>In the fourth step (traj4), the end-effector is moved from the position where it is grasping the cube to the standoff position above the initial cube position with the gripper being closed (i.e. holding the cube), cartesian trajectory is incorporated for it to move in a straight line. </li>
            <li>In the fifth step (traj5), to move the end-effector from the standoff position above the cube’s initial position to the standoff position above the cube’s final position, screw trajectory is incorporated. </li>
            <li>In the sixth step (traj6), to move the end-effector from the standoff position above the cube’s final position to the cube’s final or goal position, cartesian trajectory is incorporated. </li>
            <li>In the seventh step (traj7), the end-effector position remains the same though in that period the gripper position is changed from closed to open, cartesian trajectory is incorporated. </li>
            <li>In the eighth step (traj8), to move the end-effector from cube’s final or goal position to the standoff position at a certain z height above the cube’s final or goal position, cartesian trajectory is incorporated.</li>
        </ul>

        <strong>
        <i>
        For calculating the Feedback Control       
        </i>
        </strong>

        "

    - 
        type: image
        body: /assets/images/thumbs/youbot1.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
        
    -
        type: paragraph
        body: "
        PI control was used that made the motion smooth.<br> 
        For the new task:<br>
        Kp = 18 and Ki = 11 <br>
        The X_error plot is shown below:
        "

    -
        
        type: image
        body: /assets/images/thumbs/youbot2.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -

---
