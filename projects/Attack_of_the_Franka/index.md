---
layout: project
project_title: "Attack of the Franka"
project_caption: "Attack of the Franka Fall Project | Sept 2022."

project_content:
    - 
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/02.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        title: "Overview"
        body: "The Franka Robot which has 7-dof picks up the lightsaber and knocks down enemies represented by red blocks while protecting the allies represented by blue blocks. These enemies and allies are arbitrarily positioned.
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Description"
        body: "
        1)
        <i>Frame Positions (Computer Vision)</i>

        The transforms of the camera and workspace from the robot are obtained using AprilTags. The frames are fixed to the most recent transform so that even if the AprilTag is removed or covered by a fallen enemy, we can still know the relative positions from each other from the latest calibration.<br>
        <br>
        "
    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/attackoffranka1.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        body: "
        2)
        <i>Detections (Computer Vision)</i><br>
        The RealSense's aligned depth image is used to deproject the pixels in the RGB image into real world coordinates. For reliability, several filters are used (depth, contour area, location, and opening/closing) to ensure only the relevant objects are detected. Enemies and allies are detected, and their centroids give their position. Their labelling is sorted in x direction. The count of enemies vanquished is also calculated.        
        <br>
        "
    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/attackoffranka2.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        body: "
        3)
        <i>Franka control</i><br>
        The Franka then performs knockout motion by first checking for a left swing, stab, and then right swing possibility to knock out enemies without harming any allies, while keeping the ally safety as the highest priority. It decides to NOT execute any motion if harm of any ally cannot be avoided. <br>
        <br>
        After the Franka has held the lightsaber in the home position and the service to is called, the allies are added as collision object into the scene.

        "
    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/attackoffranka3.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        title: "Future Scope"
        body: "Develop a more robust motion planning to increase its ability to tackle plan and execute decisions for more edge cases and other position variations of enemies and allies.
        <br>
        <br>
        "
    -
        type: paragraph
        body: "
        <i><b>Team Members:</b></i><br>
        Nick Morales<br>
        Megan Sindelar<br>
        Vaishnavi Dornadula<br>
        Sushma S Chandra<br>
        <br>
        <br>
        "
    -

---

