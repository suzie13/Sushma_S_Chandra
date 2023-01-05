---
layout: project
project_title: "Jack in a Box Simulation"
project_caption: "One-liner description | Sept 2022."

project_content:
    - 
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/06.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        title: "Overview"
        body: "To simulate and animate a dynamic system of a jack in a box when the box is shaken. We are considering a side view in 2-D.
        <br>
        <br>

        The configuration variables are:<br>
        q = [x_box, y_box, θ_box, x_jack, y_jack, θ_jack]
        <br
        At the start, the box and the jack are at rest.<br>
        Below image depicts the frames I used.<br>
        "
    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/07.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    
    -
        type: paragraph
        title: "Description"
        body: "
        <br>
        <i><strong>Rigid Body transformations</strong></i><br>
        The transforms from the center of body to the world for both the box and the jack are found.<br>
        Next, the transforms of b1,b2,b3 and b4 of the box to b of the box; the transforms from d1, d2,d3,d4 of the jack to d of the jack.<br>

        To find the d1,d2,d3,d4 transforms of the jack with respect to the b1 of the box;<br>
        d1,d2,d3,d4 transforms of the jack with respect to the b2 of the box;<br>
        d1,d2,d3,d4 transforms of the jack with respect to the b3 of the box<br>
        d1,d2,d3,d4 transforms of the jack with respect to the b4 of the box<br>
        we calculate the inverse of the g_bb1, g_bb2, g_bb3 and g_bb4<br>

        <br>
        <br>
        <i><b>Forces and Constraints</b></i><br>
        <br>
        An external force of 700*sin(pi*t) is applied on the box in the x direction. A sinusoidal type of force provides a back and forth shaking motion. 700 is the amplitude and pi*t is the period; frequency=2pi/period.<br>
        And another external force of magnitude of the gravitational force acting on the box (Total mass of box*gravity*height of the box from its center of mass with respect to the world frame) is applied in the opposite direction of that gravitational force to prevent the Box from falling down and going outside the scene.<br>

        <br>
        The constraint for jack's impact with the sides of box corresponding to the b1 and b3 frame is the x-axis. <br>
        The constraint for jack's impact with the sides of box corresponding to the b2 and b4 frame is the y-axis. <br>
        <br>
        <br>
        <i><b>Impact Update Laws</b></i><br>
        Forces of gravity are acting on the total mass of the box and on the total mass of the jack. <br>
        Calculate the kinetic energy and potential energy acting on each<br>
        Langrangian = Total Kinetic energy (i.e. Box + Jack) – Total Potential energy ( i.e. Box + Jack) <br>
        For calculating the inertia Izz to use in the KE, I took 4 point masses at the corners for each, the box and the jack.<br>
        From the Langrangian we can get the Euler-Langrangian Equation and then a Euler-Langrange matrix equation where we have one side as the previous Euler Langrangian terms and the other side as the Force matrix in the q configuration.<br>
        Then find the impact equations by using the constraints matrix, substituting values in the tau plus (after impact)<br>
        Checking for impact conditions and only when there is impact solving for them.<br>

        <br>
        <br>
        <b>Graphs</b>

        "
    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/04.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg
        

    -
        type: image
        title: A caption for the above image.
        body: /assets/images/thumbs/05.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: paragraph
        body: "
        <i><b>Observation</b></i>
        <br>
        The box is shaking as expected which slowly starts to die down until the impact from the jack adds a torque to the box. The box’s height is maintained to an extent and not changing much with respect to its center of mass to the world frame and it does not fall out of the scene.<br>
        The jack due to the force of gravity acting on it always tries to fall down while staying inside the box.<br>
        The impact of the jack on the walls of the box causes the jack itself to rotate as well as bounce from one wall to another.<br>
        "
---

