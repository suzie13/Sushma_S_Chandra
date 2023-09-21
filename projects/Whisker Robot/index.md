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
        title: Whisker Robot Setup in Action <br> The Interior camera view is overlayed onto the top right corner of the Top Camera View. <br> The interior camera view is fed into an ML algorithm to determine the contact location of an object presented to the whiskers.
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
        of an object that is in contact with the whiskers of the Robot. This is inspired by how rats perceive <br>
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
        type: paragraph
        title: "Machine Learning Algorithm"
        body: " 
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
        A neural network is first used to perform a classification task i.e. to classify that the membrane <br>
        image corresponds to that when there is or isn't contact of the object to any of the whiskers. <br>
        Another neural network is then incorporated to classify if the membrane image corresponds to that <br>
        when the object has approached the whisker array from the left direction or from the right direction, <br>
        only after it has classified that the image is for a object-whisker contact point. <br>
        <br>
        Thereafter, it is noteworthy that a separate neural network performs the regression task of predicting <br>
        the x and y coordinates of the object that came in contact with the whisker array for each the left <br>
        direction and right direction contact point. This entire structure is depicted through the flow chart above. <br>
        "
    -
        type: paragraph
        title: "<i>Neural Network Structure:</i>"
        body: " 
        <br>

        The colvolution layers extracts features from the input image using filters or weights/matrices <br>
        which are like a sliding window being multiplied with the input pixels. From the convolution <br>
        layers we obtain feature maps. The MaxPooling layer results in a downsampling picking up only <br>
        the important features. In this case I have used a Max-Pooling layer with pool size (2,2),  <br>
        <br>

        The flatten layer is primary responsible for vectorization into a 1D (one-dimension),        <br>
        for feature aggregation by forming a comprehensive set of features, and to aid in transition <br>
        into fully connected layers. <br>
        <br>

        Fully Connected layers, also known as Dense layers, is responsible for end to end learning,  <br>
        used for decision-making and final predictions. It is connected to all th neurons of the previous layer. <br>                         
        Here, the model learns more abstract features from the input image. <br>
        Hyperparameter tuning like experimenting with the learning rate,number of layers, number of filters in each layer, <br>
        using batch normalization, using regularization, using dropout layers can be done to try to achieve improved results. <br>
        <br>
        <i>Below are the detailed diagram of each of the model architectures that constitute the multimodal algorithm:</i>
        <br>

        <br>
        "
    -
        type: image
        title: Classification Model Architecture (Contact/Non-Contact)
        body: /assets/images/thumbs/classification_contactnoncontact_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
        type: image
        title: Classification Model Architecture (Left Direction/Right Direction)
        body: /assets/images/thumbs/classification_leftright_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Regression Model Architecture (x,y coordinates)
        body: /assets/images/thumbs/Regression_new.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: "
        <br> Each of the models was trained and tested on full resolution images (1080,1920,3). A Total of 15,710 data samples is <br>
        collected via the automatic data collection system. After removing NaN values and suspicious data, there is 9137 data samples <br>
        remaining. Since x,y coordinate approximate ranges for contact and non-contact is decided manually, it isn't perfectly accurate. <br>
        Suspicious data is the data sample for those ranges when the object is close to the whisker but not in contact, or just touching <br>
        the whisker but has not moved the whisker causing any change in the membrane that isn't negligible.After geting rid of this <br>
        untrustworthy data, a significant improvement in results was observed in the x-coordinate and y-coordinate prediction results in <br>
        the regression model. <br>
        "
    -
        type: paragraph
        title: "Results"
        body: "
        <br>
        "
    -
        type: image
        title: Final Result of CNN Multimodal algorithm <br> In an ideal scenario, all the data points would be on the blue dashed line.
        body: /assets/images/thumbs/graph_1.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Final Result of CNN Multimodal algorithm (Individually for left and right direction) <br> In an ideal scenario, all the data points would be on the blue dashed line.
        body: /assets/images/thumbs/graph_2.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -

        type: paragraph
        title: "Accuracy"
        body: "
        <br> Accuracy(%) = (N_total/​N_correct​​)*100 <br>
        N_correct​ --> number of samples that were correctly classified. <br>
        N_total​ --> total number of samples in the dataset. <br>
        "
    -
        type: image
        title: Training and Test Accuracy across epochs for classification (Contact/Non-Contact) model
        body: /assets/images/thumbs/contactnoncontact_accuracy.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Training and Test Accuracy across epochs for classification (Left Direction/Right Direction) model
        body: /assets/images/thumbs/direction_accuracy.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Results of regression (x-coordinate, y-coordinate) model for left direction. Predicted VS Ground Truth <br> For an ideal model all of the data points would lie on the dashed red line
        body: /assets/images/thumbs/regressionleft_accuracy.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Results of regression (x-coordinate, y-coordinate) model for right direction. Predicted VS Ground Truth <br> For an ideal model all of the data points would lie on the dashed red line
        body: /assets/images/thumbs/regressionright_accuracy.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg

    -
    
        type: paragraph
        title: "Loss"
        body: "
        <br>In the classification models I used categorical coss-entropy function to calculate the loss <br>
        as the in classification there is a class (discrete value) prediction with a confidence level <br>
        or in other words probability of each of the classes it is trained on. <br>

        Whereas, in the regression model the loss function that is used here is mean squared error (MSE). <br>
        In regression, a continous value prediction is made. <br> "
    -
        type: image
        body: /assets/images/thumbs/categorical_cross_entropy.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: "
        <br>
        C = number of classes <br>
        y_true,i = true value or ground truth <br>
        y_pred,i= predicted value ​<br>
        <br>
        This formula calculates the negative log-likelihood of the true class label under the predicted class probabilities. <br>
        The goal is to minimize this loss during training. <br>
        "
    -
        type: image
        body: /assets/images/thumbs/mse.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        body: "
        <br>
        n = number of data points <br>
        Y_i = true value or ground truth<br>
        Yhat_i = predicted value <br>
        <br>
        MSE achieved on test data after 206 epochs for the regression model trained on only contact data, and only <br>
        for left direction was = 0.48461 cm^2 <br>

        MSE achieved on test data after 206 epochs for the regression model trained on only contact data, and only <br>
        for right direction was = 0.14036 cm^2 <br>
        "

    -
        type: image
        title: Training and Test Loss across Epochs for classification (Contact/Non-Contact) model
        body: /assets/images/thumbs/contactnoncontact_loss.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Training and Test Loss across Epochs for classification (Left Direction/Right Direction) model
        body: /assets/images/thumbs/direction_loss.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Training Loss across Epochs for regression left model
        body: /assets/images/thumbs/regressionleft_loss.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: image
        title: Training Loss across Epochs for regression right model
        body: /assets/images/thumbs/regressionright_loss.png" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        title: "Code"
        body: <a href="https://github.com/suzie13/Whisker-Robot-Project/tree/main ">Github Link</a>
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
        "
    -
        type: paragraph
        body: <a href="https://sense-lab.github.io/index.html ">SeNSE LAB  (Sensory and Neural Systems Engineering)</a>
    -

---

