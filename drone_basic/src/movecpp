#include "ros/ros.h"
#include "geometry_msgs/Twist.h"

int main(int argc, char **argv)
{
    ros::init(argc, argv, "drone_movement");
    ros::NodeHandle nh;
    ros::Publisher velocity_publisher = nh.advertise<geometry_msgs::Twist>("/cmd_vel", 10);
    ros::Rate loop_rate(10);

    geometry_msgs::Twist vel_msg;

    // Set constant velocity
    vel_msg.linear.x = 1.2; // Constant velocity in x-axis
    vel_msg.linear.y = 0.0; // Constant velocity in y-axis
    vel_msg.linear.z = 0.0; // Constant velocity in z-axis
    vel_msg.angular.x = 0.0; // No angular velocity
    vel_msg.angular.y = 0.0; // No angular velocity
    vel_msg.angular.z = 0.0; // No angular velocity

    while (ros::ok())
    {
        // Move up 7 meters
        ROS_INFO("Moving up 7 meters...");
        vel_msg.linear.z = 1.2; // Set velocity for upward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(7 / vel_msg.linear.z).sleep(); // Time to reach 7 meters
        vel_msg.linear.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move forward 3 meters
        ROS_INFO("Moving forward 3 meters...");
        vel_msg.linear.x = 1.2; // Set velocity for forward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(3 / vel_msg.linear.x).sleep(); // Time to reach 3 meters
        vel_msg.linear.x = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move down 3 meters
        ROS_INFO("Moving down 3 meters...");
        vel_msg.linear.z = -1.2; // Set velocity for downward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(3 / abs(vel_msg.linear.z)).sleep(); // Time to reach 3 meters
        vel_msg.linear.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move to y=1.5 meters
        ROS_INFO("Moving to y=1.5 meters...");
        vel_msg.linear.y = 1.5; // Set velocity for y-axis movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Wait for the drone to reach the desired position
        vel_msg.linear.y = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move up 1 meter
        ROS_INFO("Moving up 1 meter...");
        vel_msg.linear.z = 1.2; // Set velocity for upward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(1).sleep(); // Time to reach 1 meter
        vel_msg.linear.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move up 5 meters
        ROS_INFO("Moving up 5 meters...");
        vel_msg.linear.z = 1.2; // Set velocity for upward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(5 / vel_msg.linear.z).sleep(); // Time to reach 5 meters
        vel_msg.linear.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Angular movement to the left 3 meters
        ROS_INFO("Angular movement to the left 3 meters...");
        vel_msg.angular.z = 0.4; // Set angular velocity for left movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(3 / abs(vel_msg.angular.z)).sleep(); // Time to reach 3 meters
        vel_msg.angular.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        // Move down 6 meters
        ROS_INFO("Moving down 6 meters...");
        vel_msg.linear.z = -1.2; // Set negative velocity for downward movement
        velocity_publisher.publish(vel_msg);
        ros::Duration(6 / abs(vel_msg.linear.z)).sleep(); // Time to reach 6 meters
        vel_msg.linear.z = 0.0; // Stop
        velocity_publisher.publish(vel_msg);
        ros::Duration(2).sleep(); // Stop for 2 seconds

        ROS_INFO("Drone movement completed.");

        ros::spinOnce();
        loop_rate.sleep();
    }

    return 0;
}
