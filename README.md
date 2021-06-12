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

### Main

This program also comes with a main.cpp which run basic tests for the CLI and for the Server.
One can adjust the main and customize it to his needs. For example, it is possible to create an instance of a server that will serve clients, and act as a real Anomaly Detection Server.

## IDEs, Writers and Tools

## Notes

## Screenshots

A Linear Regression line:

