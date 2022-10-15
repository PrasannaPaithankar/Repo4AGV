# Robot Operating System Documentation
## Publisher Subscriber Node
Directly diving into the set of commands used 
```
roscore
```
After initializing all the .cpp and cmake files we execute the following on another terminal
```
rosrun beginner_tutorials talker
rosrun beginner_tutorials listener
```
Note: Run catkin_make after making changes to CMake.txt in source directory

#### Publisher node cpp file
```
#include "ros/ros.h"
#include "std_msgs/String.h"
#include <sstream>

int main(int argc, char **argv)
{
  ros::init(argc, argv, "talker");
  ros::NodeHandle n;
  ros::Publisher chatter_pub = n.advertise<std_msgs::String>("chatter", 1000);
  ros::Rate loop_rate(10);
  int count = 1;
  float sum = 0;
  while (ros::ok())
  {
    std_msgs::String msg;
    std::stringstream ss;
    ss << "DumDumDummy" << sum;
    msg.data = ss.str();
    ROS_INFO("%s", msg.data.c_str());
    chatter_pub.publish(msg);
    ros::spinOnce();
    loop_rate.sleep();
    ++count;
    sum = sum + (1/(count*count));
  }
  return 0;
}
```
#### Subscriber node cpp file
```
#include "ros/ros.h"
#include "std_msgs/String.h"

void chatterCallback(const std_msgs::String::ConstPtr& msg)
{
  ROS_INFO("I heard: [%s]", msg->data.c_str());
}

int main(int argc, char **argv)
{
  ros::init(argc, argv, "listener");
  ros::NodeHandle n;
  ros::Subscriber sub = n.subscribe("chatter", 1000, chatterCallback);
  ros::spin();

  return 0;
}
```
