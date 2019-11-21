# EEG data, binary classification(right and left hand) using deep learning
Binary classification of EEG motor imagery data using deep learning 
There are 3 CNN models(Tor2, Tor3,Tor4) proposed to classify motor imagery EEG data. We have compared them with traditional algorithms
for classification like LDA and SVM. Our models showed 65%(Tor3),66%(Tor4) and 68%(Tor2) of accuracy, while LDA and SVM showed 65% and 64% respectively. Tor2 model was based on the paper "Single-trial EEG classification of motor imagery using deep convolutional neural networks" by Tang and et.
# Data
We were provided with data of 80 healthy participants, overall 12000 trials, 39 channels. 50% of trials trials for left and 50% for right hand. We have done band pass filter(10-14Hz), Segmentation: 0.75-3.5 sec and 0-8.0 sec, Splitting to train and test sets - 80/20 and for feature extraction: CSP on train set (6 features). We are not allowed to upload data and use outside of the class.
# Tor2
68% of accuracy and AUC=0.784 for data without CSP and with segmentation 0- 8.0 sec <br/>
Net(<br/>
  (conv1): Conv2d(1, 8, kernel_size=(1, 39), stride=(1, 1))<br/>
  (batch1): BatchNorm2d(8, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)<br/>
  (dropout1): Dropout(p=0.5, inplace=False)<br/>
  (conv2): Conv2d(8, 40, kernel_size=(25, 1), stride=(25, 25))<br/>
  (batch2): BatchNorm2d(40, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)<br/>
  (dropout2): Dropout(p=0.5, inplace=False)<br/>
  (fc1): Linear(in_features=1280, out_features=100, bias=True)<br/>
  (dropout3): Dropout(p=0.5, inplace=False)<br/>
  (fc2): Linear(in_features=100, out_features=1, bias=True)<br/>
)<br/>
criterion = nn.BCEWithLogitsLoss()<br/>
optimizer = torch.optim.Adam(net.parameters())<br/>
num_epochs = 30<br/>
# Tor3
65% of accuracy and AUC=0.72 for data with CSP and with segmentation 0.75-3.5 sec <br/>
Convolution -> Batch Normalization -> Relu-> Dropout->Convolution-> Batch Normalization -> Relu-> Dropout ->fully connected><br/>
criterion = nn.CrossEntropyLoss()
nu_epochs = 20<br/>
# Tor4
66% of accuracy and AUC=0.72 for data with CSP and with segmentation 0.75-3.5 sec <br/>
Tor4(<br/>
  (conv1): Conv2d(1, 64, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))<br/>
  (conv2): Conv2d(64, 64, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))<br/>
  (fc1): Linear(in_features=105600, out_features=10, bias=True)<br/>
  (fc2): Linear(in_features=10, out_features=2, bias=True)<br/>
)<br/>
criterion = nn.BCEWithLogitsLoss()<br/>


# Authors
Aslan Ubingazhibov - Computer Science, Nazarbayev University, aslan.ubinagzhibov@nu.edu.kz <br/>
Yernar Zhetpissov - Robotics and Mechatronics, Nazarbayev University, yernar.zhetpissov@nu.edu.kz<br/>
Yerassyl Orazbek - Robotics and Mechatronics, Nazarbayev University, yerassyl.orazbek@nu.edu.kz<br/>
Daniyar Kazbek - Computer Science, Nazarbayev University, daniyar.kazbek@nu.edu.kz<br/>

# Reference
Tang, Zhichuan, Chao Li, and Shouqian Sun. "Single-trial EEG classification of motor imagery using deep convolutional neural networks." Optik-International Journal for Light and Electron Optics 130 (2017): 11-18.
