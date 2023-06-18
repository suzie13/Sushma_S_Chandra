---
layout: project
project_title: "Quadrotor Autonomous Control"
project_caption: "Quadrotor Mixed Autonomy | Jan-March 2023."

project_content:
    - 
        type: image
        title: Qudrotor Autonomous flying
        body: /assets/images/thumbs/quadrotor.gif" alt="https://www.w3schools.com/bootstrap4/paris.jpg
    -
        type: paragraph
        title: "Overview"
        body: " 
        The goal was to develop a quadrotor autopilot system that can fly autonomously. <br>
        The sub-goals of the project involved : <br>
        - control of the quadrotor manually via keyboard <br>
        - control of the quadrotor manually via joystick <br>
        - autonomous control of the quadrotor via Vive Lighthouse <br>
        <br>
        <br>
        "
    -
        type: paragraph
        title: "Hardware setup"
        body: " The harware components of the quadrotor that were assembled primarily comprises <br>
        the WIFI module, IMU (Inertial Measurement Unit) sensor, raspberry pi, 4 motors and a rechargable lithium battery.<br>
        Additional harware that was used was a joystick and vive sensor.<br>
        <br>
        <br>

        <br>
        "
    -

        type: paragraph
        title: "Control"
        body: "The roll, pitch, yaw is controlled by using PID (Proportional Integral and Derivative ) algorithm. <br>
        This allows for smooth flight in all directions with minimal overshooting or oscillations.<br>
        The PID gains were fine-tuned to gain stable and precise control of the quadrotor's orientation. <br>
        The thrust is controlled by regulating the PWM of the motors. 
        <br>
        <br>
        //Complementary filter for estimating roll and pitch angles <br>
        //using gyroscope and accelerometer data from an IMU: <br>
        roll_gyro += imu_data[1]*imu_diff; <br>
        pitch_gyro += imu_data[0]*imu_diff; <br>
        roll_angle = roll_accel*A_COMP_FILTER + (1-A_COMP_FILTER)*(roll_angle+imu_data[1]*imu_diff); <br>
        pitch_angle = pitch_accel*A_COMP_FILTER + (1-A_COMP_FILTER)*(pitch_angle+imu_data[0]*imu_diff); <br>

        //motor controls: <br>
        motor_cntrl0 = desired_thrust+desired_pitch-desired_roll-yaw_error*P_YAW-yaw_vive_error*P_VIVE_YAW; <br>
        motor_cntrl1 = desired_thrust-desired_pitch-desired_roll+yaw_vive_error*P_VIVE_YAW; <br>
        motor_cntrl2 = desired_thrust-desired_pitch+desired_roll-yaw_vive_error*P_VIVE_YAW; <br>
        motor_cntrl3 = desired_thrust+desired_pitch+desired_roll+yaw_error*P_YAW+yaw_vive_error*P_VIVE_YAW; <br>

        <br>
        <br>
        <br>
        "
    -

        type: paragraph
        title: "Safety"
        body: " When in manual control i.e while using the keyboard or joystick the heartbeat was measured <br>
        to know if the quadrotor is even connected to these input devices or not. There is a pause button that stops the motors,
        and a shutdown button that kills the program and stops the motors that is incorporated.
        There is a maximum and minimum thrust and indirect speed or neutral power assigned to the control (via keyboard or joystick).
        <br>
        There is also a maximum and minimum angle that is programmed to not exceed for either of pitch or roll.
        <br>
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

