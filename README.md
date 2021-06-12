# AnomalyDetectionServer

This repository documents my project in the Advanced Programming 1 course at Bar-Ilan University (2nd year).
In this project I have implemented a Simple Anomaly Detector program which have two main modes. It can be on learning mode, means every information it gets are considered as norm, And it can be on detection mode means the program comapre the new information it gets to the norm and check for anomalies.

## Project Structure

This project can be devided to the following five main parts:

### Part 1 - Anomaly Detection Utilities

This part include implementations of usful tools for anomaly detection such as usful functions and class.
Functions might be for example avg() which gets an array of floats and return the average value
Classes might be for exampple the class Point which represents a point.

Files: anomaly_detection_util.h, anomaly_detection_util.cpp.

### Part 2 - Time-Series and Simple Anomaly Detector

This part include the implementation of the Time-Series which is a C++ object that holds the data whether it is a learning data or a testing data. The data might inserted to the program via CSV files or by streaming over TCP, so the Time-Series can hold it in the RAM and give usful function to use.
This part also include the implementation of the simple anomaly detector which is looks for anomalies from a linear regression line it creates in the learning stage.

Files: AnomalyDetector.h, timeseries.h, timeseries.cpp, SimpleAnomalyDetector.h, SimpleAnomalyDetector.cpp.

### Part 3 - Hybrid Anomaly Detector

This part include an implementation of another anomaly detection algotihem based on circular anomaly. It uses Welzl algorihtm to find the Minimal Enclosing Circle (MEC) and find anomalies according to it.
This part also include an implementation of the Hybrin Anomaly Detector that knows how to use both the simple detector and, if it couldn't find a linear regression line, it will look for a circular anomaly with Welzl algorithm.

Files:  minCircle.h, minCircle.cpp, HybridAnomalyDetector.h, HybridAnomalyDetector.cpp.

### Part 4 - Command Line Interface

The previous 3 parts are about implementing the algorithm and the "backend" of the program.
In this part I have created a CLI that gives a user a way to communicate with the program.

Files: commands.h, CLI.h, CLI.cpp.

### Part 5 - Server Deployment

Finally, I have implementd a TCP threaded server that allocate a thread for each client that addresses it over TCP.
The client can send the server commands using the CLI and can get response from the server.
To mark the end of the data that the client send to the server, it should send "done".

An input example is located in the folder tests in a file named "Server_input.txt".

Files: Server.h, Server.cpp.

### Main

This program also comes with a main.cpp which run basic tests for the CLI and for the Server.
One can adjust the main and customize it to his needs. For example, it is possible to create an instance of a server that will serve clients, and act as a real Anomaly Detection Server.

## IDEs and Writers

1. JetBrains CLION
2. Visual Studio Code
3. Notepad++

## Notes

1. Command Design Pattern is implemented in this project -- In the implementation of the CLI.
2. This project uses C++ Threads and an example of Client-Server architecture.

## Screenshots

A Linear Regression line:

![image](https://user-images.githubusercontent.com/72878018/121783670-a7871180-cbb8-11eb-8139-a0c5c0cbc3a4.png)


An example of a non-correlative scattering

![image](https://user-images.githubusercontent.com/72878018/121783689-c38ab300-cbb8-11eb-90ae-57da2055987b.png)


Command Design Pattern:

![image](https://user-images.githubusercontent.com/72878018/121783737-00ef4080-cbb9-11eb-86fa-1727fa95790b.png)

![image](https://user-images.githubusercontent.com/72878018/121783764-2da35800-cbb9-11eb-82ce-c0190786ec8e.png)


How the CLI looks like:

![image](https://user-images.githubusercontent.com/72878018/121783776-414ebe80-cbb9-11eb-9865-65b7429107aa.png)


How a correlation looks like:

![image](https://user-images.githubusercontent.com/72878018/121783802-64796e00-cbb9-11eb-9ec4-a0d5b697d9a8.png)

The numbers are TimeSteps and the Letteres represents correlated features.


Server Client Architecture:

![image](https://user-images.githubusercontent.com/72878018/121783836-968ad000-cbb9-11eb-875f-b5ea9d2cff9f.png)
