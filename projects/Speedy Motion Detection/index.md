---
layout: project
project_title: "Speedy Motion Detection"
project_caption: "Speedy Motion Detection | May 2023."

project_content:
    - 
        type: image
        title: Speedy Motion Detection on random falling objects
        body: /assets/images/thumbs/falling.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        title: "Overview"
        body: " This project is built from scratch with minimal use of black-box libraries. <br>
        The motivation for this project was child safety, when left alone at home, are in danger <br>
        of speedy moving objects and an alert can be sent to the parent. The algorithm can also <br>
        detect any object (of any size, shape, color, both living and non-living objects). It can also <br>
        be used to detect elderly people falling down. This application can particularly prove to be <br>
        useful in regions prone to earthquakes, and also at construction sites. <br>
        <br>
        <br>
        This project integrates a static background and utilizes a single point perspective camera view. <br>
        The algorithm ensures to only detect objects moving with a speed greater than a certain threshold.
        "
    -
        type: paragraph
        title: "Design"
        body: "
        <br>
        <br>
        The algorithm's computational demands are significantly reduced as it avoids the use of neural networks. <br>
        Consequently, it can swiftly track objects in real-time, proving particularly advantageous when rapid <br>
        detections are essential in this specific application.This project is camera type independent where <br>
        the resolution doesn’t affect the algorithm and image processing and even low resolution <br>
        video can perform the task efficiently. Each step can be depicted visually, enhancing <br>
        transparency and facilitating better comprehension and understanding of each individual <br>
        action. <br>
        <br>
        "
    -
        type: paragraph
        title: "Algorithm"
        body: "
        <br>
        This algorithm can be broken down into four main steps, namely motion masking, <br>
        connected component labelling, object id and tracking, and speed filter. In motion <br>
        masking the pixel intensities are compared between frames, in connected component <br>
        labelling different objects get different labels, then a unique id is extracted for unique <br>
        objects and are tracking by calculating the similarity score of each object. Lastly, a speed <br>
        filter is applied to only track those objects which are not just moving but having a <br>
        speedy motion.
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Demonstrations"
    -
        type: image
        title: "Non-falling or non speedy motion"
        body: /assets/images/thumbs/nonfalling.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: "
        <br>
        <br>
        "
    -
        type: image
        title: "Simultaneous Moving objects demo"
        body: /assets/images/thumbs/simult_falling.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: paragraph
        body: "
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Future Scope"
        body: " 
        Machine learning can be used for object similarity <br>
        Eliminate shadow tracking <br>
        Use other technique like edge detection like OpenCV Canny Edge Detection <br>
        Instead of bounding boxes, obtain object shapes by using segmentation techniques
        <br>
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Youtube Link"
        body: <a href="https://www.youtube.com/watch?v=5dqbXpmGwbc ">Video Presentation Link</a>
    -
        type: paragraph
        body: "
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Project Partner"
        body: " Charles Cheng
        <br>
        <br>

        <br>
        "
    -

---

