# Multi-Threading-CPP
![output_image](./images/Traffic_Signal.gif)

Traffic signal control for safe driving using C++. There are two rules to cross a junction by any vehicle (moving circles)
* wait unless the traffic signal associated to that junction is green.
* whoever comes first in the junction, gets the first entry into the jnction (FIFO).

Each vehicle runs in a seperate thread. Further, each junction (intersection) maintains a seperate thread to keep track of the traffice-lights states (red/green) and how many vehicles are waiting to get into the junction. Whenever a vehicle enters into a junction, it randomly selects the next destination junction which are immediately connected to the current junction.
