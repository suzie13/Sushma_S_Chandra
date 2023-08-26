---
layout: project
project_title: "Whisker Robot"
project_caption: "Whisker Robot | April-August 2023."

project_content:
    - 
        type: image
        title: Whisker Robot
        body: /assets/images/thumbs/image_neww.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Whisker Robot Setup in Action <br> The Interior camera view is overlayed onto the top right corner of the Top Camera View.
        body: /assets/images/thumbs/Frontpage_new.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: " 
        <br>
        "
    -
        type: paragraph
        title: "Motive"
        body: " The main goal is to make the robot be able to tell the position (x-coordinate, y-coordinate) <br>
        of an object that is in contact with the whiskers of the Robot. This is inspired by how rats are able to obtain <br>
        information about their surrounding environment with the help of their whiskers. <br>
        <br>

        "
    -
        type: paragraph
        title: "Hardware Setup"
        body: "
        <br>

        There is a Whisker Robot, and an xy-plotter, both enclosed within an arena. They are actually clamped <br>
        to the table to avoid any movement of either the Whisker Robot or the xy-plotter setup. There is a  <br>
        top camera, obtaining the top view of the hardware setup, a front-camera obtaining a front-view of the <br>
        Whisker Robot and the object that is made to contact the whiskers, then there is an interior camera <br>
        mounted inside the Whisker Robot which captures images of the membrane which is attatched to the whiskers. <br>
        This membrane changes with changes in the position of any of the 9 whiskers of the whisker array. <br>
        <br>

        "
    -
        type: image
        title: Hardware Setup
        body: /assets/images/thumbs/Hardware_Setup_resized_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: image
        title: Interior Camera View
        body: /assets/images/thumbs/membrane_resized.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    - 
        type: image
        title: Top View
        body: /assets/images/thumbs/topview.jpg" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    - 
        type: image
        title: Front View
        body: /assets/images/thumbs/frontview.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: paragraph
        title: "Automatic Data Collection"
        body: "
        <br>

        I designed an automatic data collection system. An aruco marker is placed on the Whisker Robot which is stationary, <br>
        and another aruco marker on the part of the xy-plotter that moves along with the object the same magnitude and in  <br>
        the same direction. Therefore, using these two aruco markers which is read from the top camera, the object position <br>
        relative to the Whisker Robot is acquired/calculated. The object is moved by a step size of two units (approximately 0.89mm) <br>
        according to the xy-plotter in the direction that is across (perpendicular) to the whisker array and by a step size of two units <br>
        according to the xy-plotter (equivalent to approximately 0.66mm) in the direction along (parallel) to the whisker array. <br>
        It is important to note that the xy-plotter is not a perfect square hence the difference in the step size value across x and y. <br>
        After completing to traverse the entire breadth of the xy-plotter through mutliple steps, the object is moved a step parallel <br>
        to the whisker array and this process continues until it reaches the start (0,0) point of the xy plotter which is the closest <br>
        possible to the Whisker Robot along the direction parallel to the whisker array. <br>
        <br>
        <br>

        After the completion of each step, there is a pause of about 2 seconds before the xy-plotter is instructed to take the next step.<br>
        During this pause, an image of the membrane which might of might not have changed slightly depending on the contact or no contact <br>
        of the object to part or whole of the whisker array, is captured. The image is saved with a name i.e 'Serialno._Timestamp', where <br>
        the Serial_no. is indicative of the order in which the images are captured and the timestamp is indicative of the time <br>
        (YY-MM-DD-HH-MM-&#181S). At the same instance, data is collected/stored in a csv file having the same serial number and timestamp <br>
        under their respective columns, along with the x-coordinate and y-coordinate information as obtained by the aruco markers detected <br>
        from the top camera, the direction in which the object was brought in contact with the whiskers (i.e left or right) is stored, and <br>
        the x-step and y-step information as per the x-y plotter is stored as well. Due to motors slipping, the object might not end up at <br>
        the commanded position each time thereby the x-step and y-step giving an incorrect indication of the actual position of the object. <br>
        This issue is accounted for as the x,y coordinates information is collected via the top camera using aruco markers yielding far <br>
        more accurate readings. <br>

        <br>
        "
    - 
        type: image
        title: Sample Dataset (Color coded with serial number which represents increment in Time)
        body: /assets/images/thumbs/Automatic_Data_Collection.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: " 
        <br>
        "
    -
        type: paragraph
        title: "Data Preprocessing"
        body: " 
        <ul>
            <li> Correlate interior camera membrane images with coordinate information of the object based on Serial no. </li>
            <li> Remove NaN/missing values </li>
            <li> One hot encoding, specifically Label Encoder for direction (left and right in words to 0 and 1)
            </li>
            <li>Remove outliers or suspicious(since contact and non-contact range is decided manually, \
            there is a time when the object(vertical peg) in this case is close to the whisker but not in contact) \
            data during training the model(outlier detection)</li>
            <li> In the model for classification of contact and non-contact there is some additional pre-processing required.  </li>
            <li> The classes were unbalanced, i.e. the non-contact datasamples was around 7800 whereas the contact datasamples \
             was around 1600. Since all the non-contact membrane images are exactly the same, there wouldn't be loss of information by reducing
             the non-contact datasamples, the non-contact datasamples were downsampled and made equal to the number of 
             contact datasamples. </li>
            <li> Performed stratified split to ensure there is a percentage of each class in the same ratio in both train \
            and test dataset. </li>


        </ul>
        <br>

        <br>
        "
        
    -
        type: image
        title: Multimodal Flow Chart
        body: /assets/images/thumbs/Multimodal_Flowchart_resized.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: "
        <br>
        The colvolution layers extracts features from the input image using filters or weights/matrices <br>
        which are like a sliding window being multiplied with the input pixels. From the convolution <br>
        layers we obtain feature maps. The MaxPooling layer results in a downsampling picking up only <br>
        the important features. In this case I have used a Max-Pooling layer with pool size (2,2),  <br>
        <br>
        <br>
        The formula to calculate the output shape of a Conv2D layer is: <br>

        Output height = (Input height - Filter height + 2 * Padding) / Stride + 1 <br>
        Output width = (Input width - Filter width + 2 * Padding) / Stride + 1 <br>

        <br>
        Too calculate output shape after the Max Pooling layer: <br>
        ((input height/pool size), (input width/pool size), number of channels) <br>
        <br>

        The flatten layer is primary responsible for vectorization into a 1D (one-dimension),        <br>
        for feature aggregation by forming a comprehensive set of features, and to aid in transition <br>
        into fully connected layers. <br>
        <br>
        Therefore, the output shape is simply: input height * input width * number of channels <br>
        <br>
        Fully Connected layers, also known as Dense layers, is responsible for end to end learning,  <br>
        used for decision-making and final predictions. It is connected to all th neurons of the previous layer. <br>                         
        Here, the model learns more abstract features from the input image. <br>
        Hyperparameter tuning like experimenting with the learning rate,number of layers, number of filters in each layer, <br>
        using batch normalization, using regularization, using dropout layers can be done to try to achieve improved results. <br>

        <br>

        <br>
        "
    -
        type: image
        title: Classification Model Architecture (Contact/Non-Contact)
        body: /assets/images/thumbs/classification_contactnoncontact_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: image
        title: Classiffication Model Architecture (Left Direction/Right Direction)
        body: /assets/images/thumbs/classification_leftright_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Regression Model Architecture (x,y coordinates)
        body: /assets/images/thumbs/Regression_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        title: "Results"
        body: "
        <br>
        <br>

        <br>
        "
    -
        type: paragraph
        title: "Accuracy"
        body: "
        <br>
        <br>

        <br>
        "
    -
        type: paragraph
        title: "Loss"
        body: "
        <br>
        <br>

        <br>
        "
    -
        type: paragraph
        body: " Github Link
        <br>hmm
        <br>

        <br>
        "
    -
        type: paragraph
        title: "Future Scope"
        body: "
        <br>The future scope of this project is to obtain not just a 2D perspective (x,y coordinates) \
        of the object but the 3D perspective (x,y and z coordinates) of the points of contact of object \
        to the whisker. To further elaborate this, the objective is to obtain a point cloud of all the \ 
        contact points (9 contact points) of object to the whisker, thereby better enabling to reconstruct \
        the object that came in contact with the whisker of the Whisker Robot through whisking.
        <br>
        <br>
        " 
    -
        type: paragraph
        title: "Acknowledgements"
        body: "
        <br>
        Dr. Mitra Hartmann (Principle Investigator at SeNSE LAB) <br>
        Mr. Kevin James Kleczka (Research Engineer at SeNSE LAB) <br>
        Professor Matthew Elwin (Co-Director of MS in Robotics program) <br>
        <br>
        SeNSE LAB  (Sensory and Neural Systems Engineering) <br>
        (Link) https://sense-lab.github.io/index.html
        <br>

        <br>
        "
    -

---

