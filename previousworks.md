---
layout: page
title: Previous Works
subtitle: Created By Vincent Lee
---

-----
<center><h1> Paca Pace </h1></center>
-----

# Project Description

The objective of this application is to detect the cadence or RPM (revolutions per minute) of a cyclist and to appropriately notify when the user have reached or is deviating from their ideal cadence. The android program that we call “Paca Pace” will be integrated alongside our Mobile Health Sensing app. The slogan for ur objective is to “run like an alpaca, be the alpaca.”

## Motivation 

There are numerous outdoor cycling apps, but very few indoor apps.  Paca Pace is will provide a niche in the cycling realm by giving athletes the abilities to track their cadence without the use of expensive bike attachments and computers.  All that is required is a durable armband that you will be strapping them to your leg.
Ideally, Paca Pace will help push all athletes to maintain a consistent cadence of 90 throughout their workout.  By having a consistent pace of 90 RPM, cyclists will reduce hip injuries and will overall improve their finish times during race seasons.  

## Sensors

The list of possible sensors that we may or may not be using for data collection:
- Accelerometer
- Vibrations
- Camera (PPG)
- ECG Band

# Data Collection

Similar to the step-detection activity, we will start collecting cycling movements by having our phones strapped to our leg with smartphone band used to record the accelerometer readings. Eventually we will collect multiple readings for accelerometer and vibrations expecting to see a pattern for RPM.
As a stretch goal, we would use the Mcrowd Viz app to collect additional data for looking at speed, velocity, and power. The visualization would aid in creating higher precision and accuracy for our RPM detection. We can also use WEKA for creating an activity recognition by detecting stopping and speeding.

$ Approach

Once we collect our data, we create an algorithm that will provide the moving average RPM using the accelerometer.  We will be looking at our past step detection assignment as a model for developing the RPM detection algorithm.  
Real time RPM data will be delivered to the UI every 5 seconds. We will also look into using phone’s vibrations to determine additional noise and movement.

# Visualization

The idea is to create a visualization of the accelerometer so you can see the RPM movement:
Line Graphs
Bar Graphs
Meters
Status Bar

# Stretch Goals

Our main focus is to collect accurate data for displaying the cadence or RPM. The stretch goals are ambitious activities or challenges that we may integrate after finishing our main objective. 
- Use of Speed / Velocity Data
- Activity Recognition
- Saving features
- Visualization
- Android Wear Integration
- Notification System
= Availability to input different RPM and ranges
- Integration with heart rate data
