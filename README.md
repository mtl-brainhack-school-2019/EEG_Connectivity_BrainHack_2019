# DECODING EEG single trials and connectomes
## This is my repo for my project of [MONTREAL BRAINHACK SCHOOL](https://brainhackmtl.github.io/school2019/) from 5th to 30th August 2019.
***
* I would like to assess EEG task-related single trials and functional connectivity using machine learning tools and/or MNE library. 
* [OHBM Poster of the project](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/Anne_Monnier_OHBM_Connectomes.pdf "Poster")
* RAW DATA: Scalp EEG data - Biosemi - 512 Hz - 64 electrodes - 50 healthy humans 
* TASK: Visuo-spatial attention task (about 250 trials per Main condition per subject)

## Pre-processed Data (from EEGLAB to PYTHON)
- [X] For ERP: On continuous signal (Raw, .bdf), blinks and artefacts filtered and then segmented (.set + .ftd)
- [X] For wPLI:  On continuous signal, SCD applied (Raw, .bdf), blinks and artefacts filtered, 14 electrodes selectionned, Beta and Gamma filtered and Hilbert transform applied and wPLI (.erp), and then 10 ICA (connectomes) (.mat)
- [ ] Data dimension structured as epochs, to be compliant with Python process (initially EEGLAB/MATLAB)

## GOAL (1) Classify into 2 clusters whatever Epoch: Attended vs Ignored
* __THE PROBLEM IN WORDS__: Each epoch, as a voltage signal (ERP) or a feature weight (ICA), will be the input to a two-state classifier (attended vs ignored). The performance of the classifier will provide a multivariate analysis showing in what time periods the features support classification, and which contribute more.
* __ALGORITHM__: Train a regression model (or a __LDA__, or SVM model) to classify trials in 2 groups. 
* Identify which connectome(s) and during which time course is relevant to this attending / memorizing process.
* --> Find a performance values (accurancy...) publishable !! and a nice vizualization !!!!

## GOAL (2) Implement Granger Causality function for a relevant link
* __DATASET (.set)__: The analyses will use the Hilbert transform data of each channel of relevant link (/91).
* __PREPROCESS__: Identify a link from a connectome with Beta/Gamma relevant for differentiating the 2 modes
* __ANALYSE__: Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

- - - -

## Challenges 
- [X] Settle my Environnement on MY COMPUTER: Visual Box + Ubuntu + Pyhton 3.6 + MNE + Jupyter.
- [X] Settle my Environnement on POWERFUL REMOTE CUMPUTER in my lab
- [X] Arrange / preprocess the first DATASET (.set)
- [ ] Find the right architecture and algorithme (LDA/SVD...) for classifier and GC (find a template on github...)
- [ ] Find a nice visualization of results with 2 clusters

## Deliverables for Brainhack school :muscle: :muscle: :muscle:
- [ ] Create a video explaining my project
- [ ] Create a Jupyter Notebook with the code of a classifier
- [ ] Extract the stats
- [ ] Use matplotlib/Seaborn for visualizing features
