# EEG_Connectivity_BrainHack_2019
### This is my repo for my project of [MONTREAL BRAINHACK SCHOOL](https://brainhackmtl.github.io/school2019/) from 5th to 30th August 2019.
***
* I would like to assess task-related EEG functional connectivity using machine learning tools and/or MNE library. 
* [OHBM Poster of the project](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/Anne_Monnier_OHBM_Connectomes.pdf "Poster")
* RAW DATA: Scalp EEG data - Biosemi - 250 Hz - 64 electrodes / 50 healthy humans 
* TASK: Visuo-spatial attention task (x trials per Main condition)
* HYPOTHESE : Phase synchrony in γ band underlies feedforward (green) and in β band underlies feedback communication (blue) (proved on iEEG on Macaques and MEG). The project consists in identifying the same phenomenon in EEG: extracting wPLI connectomes in γ and β band that are relevant for encoding a visual stimulus in working memory. 
* [<img src="https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/pascal_fries.jpg" width="300" height="200">]

## Pre-processed Data
- [X] On continuous signal, blinks and artefacts filtered + scalp current density (avoid volume conduction) (.bdf)
- [X] 14 electrodes selectionned: Beta and Gamma filtered and Hilbert transform applied (.set)
- [X] On 91 links, wPLI calculated for each band, then epoched on 800 ms. (.erp)
- [X] PCA/ICA applied on beta and Gamma wPLI for 10 components (Screeplot) (.mat)
- [ ] Convert/concatenate/label (attended / Ignored) .mat form EEGLAB to sklearn compliant Dataset
- [ ] Data dimension structured to be compliant with Python process (initially EEGLAB/MATLAB)

## GOAL (1) Classify into 2 clusters: Attended vs Ignored
* DATASET IS MATRICES(.mat): The analyses will use the matrix of 10 connectomes (ICA components) time course to decode the 2 modes
* THE PROBLEM IN WORDS: Each component time course, as a feature weight, will be the input to a two-state classifier (attended vs ignored). The performance of the classifier will provide a multivariate analysis showing in what time periods the features support classification and which contribute more.
* ALGORITHM: Train a regression model (or a LDA, or SVM model) to classify trials in 2 groups. 
* Observe / Identify / and Visualize which connectome(s), and during which time course is relevant to this attending / memorizing process.
* --> Find a statistical value publishable and vizualization way

## GOAL (2) Implement Granger Causality function for a relevant link
* DATASET IS (.set): The analyses will use the Hilbert transform data of each channel of relevant link.
* PREPROCESS: Identify a link from a connectome with Beta/Gamma relevant for differentiating the 2 modes
* ANALYSE: Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

## Challenges / to do list
- [ ] Settle my Environnement of work: Visual Box + Linux + Pyhton 3.6 + MNE + Jupyter ...
- [ ] Find the right architecture / package for cluster analyse
- [ ] Find the right architecture / package for Granger Causality analyse
- [ ] Make sens of the problem I pose: it could be decoded with the P3... so what is the added value of connectivity ?

## Machine Learning architecture
- [ ] Use pandas and sklearn
- [ ] Separate data: Train, Validation, Test
- [ ] Define Architecture: Train network on 50 subjects and X trials on remaining 2 subjects -> accuracy good enough ? How many folds ?
- [ ] Choose parameters for good trial classifier
- [ ] Confusion matrix for trial prediction

## Deliverables for Brainhack school
- [ ] Jupyter Notebook explaining all the process steps
- [ ] Training and Data preparation files added with some comments
- [ ] Use matplotlib/Seaborn for visualizing features
- [ ] R code for getting the stats ?
