# Deep_learning_EEG_Classification

This project reproduces supervised feature learning & classification of mental states from EEG measures. It takes its roots in the following papers and githubs:

Bashivan, et al. "Learning Representations from EEG with Deep Recurrent-Convolutional Neural Networks." International conference on learning representations (2016).

https://github.com/BashivanLab/EEGLearn
https://github.com/tevisgehr/EEG-Classification
Ribeiro, et al. "Why should I trust you? : Explaining the Predictions of Any Classifier". International conference on knowledge discovery and data mining (2016).
https://github.com/marcotcr/lime

This code allows the classification of cognitive states through convolutional neural nets, with generation of spatial and spectral structures preserving cognitive maps.
This specific code classifies cognitive loads (0,1, 2 or 3) using as data spectral power within three prominent frequency bands, theta (4-7Hz), alpha (8-13Hz), and beta (13-30Hz), recorded by 64 electrodes whose 3D positions are also given in the dataset. 
These dataset is accessible through https://github.com/BashivanLab/EEGLearn, downloading the "Sample data" folder (2670 samples, weight of 55.1Mo).

Each spectral power value of the 3 frequency bands is associated to a brain location thanks to 3D positions of the 64 electrodes and their topology-preserving azimuthal equidistant projections. For each trial, the averaged values of the 7 frames are used to form topographical maps for each frequency band (theta, alpha, beta). These maps are then combined to form 3-channel images which are fed into a convolutional network for representation learning and classification.
Two convolutional networks are presented for this classification, as well as some insights on the specific elements driving their classification, using LIME technique.
