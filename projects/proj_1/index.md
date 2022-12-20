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
        body: "To simulate and animate a dynamic system of a jack in a box when the box is shaken. We are considering a side view in 2-D.
        
        <br/>
        <br/>

        The configuration variables are:
        <br/>
        q = [x_box, y_box, θ_box, x_jack, y_jack, θ_jack]
        "
    
    -
        type: paragraph
        body: "
        At the start, the box and the jack are at rest.
        Below image depicts the frames I used."
    
    -
        type: paragraph
        title: "Rigid Body transformations"
        body: "The transforms from the center of body to the world for both the box and the jack are found.
        Next, the transforms of b1,b2,b3 and b4 of the box to b of the box; the transforms from d1, d2,d3,d4 of the jack to d of the jack.
        To find the d1,d2,d3,d4 transforms of the jack with respect to the b1 of the box;
        d1,d2,d3,d4 transforms of the jack with respect to the b2 of the box;
        d1,d2,d3,d4 transforms of the jack with respect to the b3 of the box
        d1,d2,d3,d4 transforms of the jack with respect to the b4 of the box
        we calculate the inverse of the g_bb1, g_bb2, g_bb3 and g_bb4
        "
---
