# EEGclassification
Binary classification of EEG motor imagery data using deep learning 
There are 3 CNN models(Tor2, Tor3,Tor4) proposed to classify motor imagery EEG data. We have compared them with traditional algorithms
for classification like LDA and SVM. Our models showed 65%(Tor3),66%(Tor4) and 68%(Tor2) of accuracy, while LDA and SVM showed 65% and 64% respectively. Tor2 model was based on the paper "Single-trial EEG classification of motor imagery using deep convolutional neural networks" by Tang and et.
# Data
We were provided with data of 80 healthy participants, overall 12000 trials, 39 trials. We have done band pass filter(10-14Hz), Segmentation: 0.75-3.5 sec and 0-8.0 sec, Splitting to train and test sets - 80/20 and for feature extraction: CSP on train set (6 features). We are not allowed to upload data and use outside of the class.
# Authors
Aslan Ubingazhibov - Computer Science, Nazarbayev University, aslan.ubinagzhibov@nu.edu.kz <br/>
Yernar Zhetpissov - Robotics and Mechatronics, Nazarbayev University, yernar.zhetpissov@nu.edu.kz<br/>
Yerassyl Orazbek - Robotics and Mechatronics, Nazarbayev University, yerassyl.orazbek@nu.edu.kz<br/>
Daniyar Kazbek - Computer Science, Nazarbayev University, daniyar.kazbek@nu.edu.kz<br/>

# Reference
Tang, Zhichuan, Chao Li, and Shouqian Sun. "Single-trial EEG classification of motor imagery using deep convolutional neural networks." Optik-International Journal for Light and Electron Optics 130 (2017): 11-18.
