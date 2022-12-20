---
layout: project
project_title: "Attack of the Franka"
project_caption: "One-liner description | Sept 2022."

project_content:
    - 
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/08.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        title: "Overview"
        body: "To track a pen autonomously and grab it.
        <br>
        <br>

        <strong>Hardware</strong>
        <ul>
            <li>PincherX 100 robotic arm</li>
            <li>Intel Realsense D435i camera</li>
        </ul>
        <br>
        <br>
        <b>Skills</b>
        <ul>
            <li>ROS</li>
            <li>OpenCV</li>
            <li>Computer Vision</li>
        </ul>


        "
    -
        type: paragraph
        title: "Description"
        body: "To track a pen autonomously and grab it.
        <br>
        <br>

        The Intel Realsense D435i depth camera is used to get the 3D position of the pen. Computer vision is incorporated to perform edge detection based on hsv color mask, gets the contours of the purple pen.<br>
        <br>
        The PincherX 100 robotic arm which has a 4 degree of freedom tracks the pen and moves to the coordinates of the detected purple pen and grabs the pen by closing its grippers, comes to the home position and opens its grippers to drop the pen.        
        <br>
        "
---

