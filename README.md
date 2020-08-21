# CNN_LSTM Model for Human Activity Recognition

Human Activity Recognition (HAR) from smartphone sensors signal dataset from [UCI Machine Learning Repositry](https://archive.ics.uci.edu/ml/machine-learning-databases/00240/UCI%20HAR%20Dataset.names)
The goal is to classify the type of movement amongst six activities:
- Walking
- Walking Upstairs
- Walking Downstairs
- Sitting
- Standing
- Laying

## Dataset

The link below shows a video of the 6 activities recorded in the experiment with one of the participants:

<p align="center">
  <a href="http://www.youtube.com/watch?feature=player_embedded&v=XOEN9W05_4A
" target="_blank"><img src="http://img.youtube.com/vi/XOEN9W05_4A/0.jpg"
alt="Video of the experiment" width="400" height="300" border="10" /></a>
  <a href="https://youtu.be/XOEN9W05_4A"><center>[Watch video]</center></a>
</p>

## Dataset Description

> The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used.

The almost raw data will be used: only the gravity effect has been filtered out of the accelerometer as a preprocessing step for another 3D feature.

## Dataset Overview

The dataset is a recording of 30 people's smartphone signal while performing the different aforementioned activities.
Each of the 3 signals (Body Acceleration, Angular Velocity, Total Acceleration) are recorded as 3-axial (xyz) data points.

There are 10,299 observations within the dataset, with training and test set split at 70% / 30%.

<img src="img/activity count.png">

## Data Visualisation

Simple lineplot for each activity was produced:
<p>
e.g. Standing vs Walking
    
<img src="img/Signals Standing.png"><img src="img/Signals Walking.png">

This is a misrepresentation of the xyz axial data being separated as different lines, therefore 3D plot is produced instead.
<p>
e.g. Body Acceleration: Standing vs Walking

<div class="row">
  <div class="column">
    <img src="img/3D Body acceleration Standing.png" alt="Standing" style="width:35%">
  </div>
  <div class="column">
    <img src="img/3D Body acceleration Walking.png" alt="Walking" style="width:35%">
  </div>

The above 3D plot is difficult to interpret and human eyes cannot distinguish when the observation starts and ends. A treatment of the 3-axial data to calculate the distance of the data point at each timesteps from the origin (x,y,z=0,0,0)
<p>
e.g. Body Acceleration: Standing vs Walking
  
<div class="row">
  <div class="column">
    <img src="img/distance Body acceleration Standing.png" alt="Standing" style="width:50%">
  </div>
  <div class="column">
    <img src="img/distance Body acceleration Walking.png" alt="Walking" style="width:50%">
  </div>

The above graphs can clearly present the notable difference in pattern between the different activities.

## Model

The CNN-LSTM model was trained with data directly feeding into the neural network without feature engineering.

GridSearchCV was used for hyperparameter tuning, and EarlyStopping was applied on the final model.
    


## Results

To be added...

## References

The [dataset](https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) can be found on the UCI Machine Learning Repository:

> Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. A Public Domain Dataset for Human Activity Recognition Using Smartphones. 21th European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning, ESANN 2013. Bruges, Belgium 24-26 April 2013.

## Afterwords

This is my final project for the Ironhack Data Analytics bootcamp, the presentation has won the data analytics category at the Ironhack Hackshow Paris August 2020.

<p align="center">
  <a href="https://ironhack.zoom.us/rec/share/7JxQLbHy3DtIT6fkq0r9f5wYGKe9X6a8gXMWrPsLxEgOztkzkZT6OitgEewzcP5X?startTime=1597680785000
" target="_blank"><img src="Annotation 2020-08-08 183436.jpg"
alt="Hackshow Paris August 2020" width="400" height="300" border="10" /></a>
  <a href="https://ironhack.zoom.us/rec/share/7JxQLbHy3DtIT6fkq0r9f5wYGKe9X6a8gXMWrPsLxEgOztkzkZT6OitgEewzcP5X?startTime=1597680785000"><center>[Watch video at 00:31:10]</center></a>
</p>

I would like to extend my gratitude to my tutor [Eldiias](https://github.com/Eldiias/) who has helped me in the understanding of the Neural Networks.

### Contact Me

- [LinkedIn](www.linkedin.com/in/sylvianclee)
- [GitHub](https://github.com/nclee17/)
