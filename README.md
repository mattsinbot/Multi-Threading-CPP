# Multi-Threading-CPP
Traffic signal control for safe driving using C++. There are two rules to cross a junction by any vehicle (moving circles)
* wait unless the traffic signal associated to that junction is green.
* whoever comes first in the junction, gets the first entry into the jnction (FIFO).

Each vehicle runs in a seperate thread. Further, each junction (intersection) maintains a seperate thread to keep track of the traffice-lights states (red/green) and how many vehicles are waiting to get into the junction. Whenever a vehicle enters into a junction, it randomly selects the next destination junction which are immediately connected to the current junction.

Please note, classes like **Vehicle**, **Intersection**, **TrafficeLight** and **Street** are all derived from the base class **TrafficObject**. More specifically, all these derived classes *override* the *simulate* method of the base class **TrafficObject**. 

Further, the **Graphics** class is responsible for plotting the relevant objects at a frequency of **1 millisecond**. It uses **OpeCV** to plot the frames at the specified rate. The plotting mechanism is as following, (a) plot the map (background) as a static image first. Then overlay two transparent images one for the animating traffic-light and another for animating the vechiles.

![output_image](./images/Traffic_Signal.gif)

I have compiled the project using C++11 standard linked with -pthread and -opencv in NetBeans IDE. The screen-shots for the build instructions in NetBeans IDE can be found in the folder named **build_setting_instructions**.
