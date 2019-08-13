# EEG_Connectivity_BrainHack_2019
### This is my repo for the project I've been working on during the [MONTREAL BRAINHACK SCHOOL](https://brainhackmtl.github.io/school2019/) from 5th to 30th August 2019.
***
* I would like to assess task-related EEG functional connectivity using machine learning tools and MNE library. 
* [OHBM Poster of the project](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/Anne_Monnier_OHBM_Connectomes.pdf "Poster")
* RAW DATA: Scalp EEG data - Biosemi - 250 Hz - 64 electrodes / 50 healthy humans 
* TASK: Visuo-spatial attention task (x trials per Main condition)
* HYPOTHESE : Phase synchrony in γ band underlies feedforward (green) and in β band underlies feedback communication (blue) (proved on iEEG on Macaques and MEG). The project consists in identifying the same phenomenon in EEG: extracting wPLI connectomes in γ and β band that are relevant for encoding a visual stimulus in working memory. 
* [<img src="https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/pascal_fries.jpg" width="300" height="200">]

## Pre-processed Data
- [X] On continuous signal, blinks and artefacts filtered + scalp current density (avoid volume conduction) (.bdf)
- [X] 14 electrodes selectionned: Beta and Gamma filtered and Hilbert transform applied
- [X] On 91 links, wPLI calculated for each band, then epoched on 800 ms. 
- [X] PCA/ICA applied on beta and Gamma wPLI for 10 components (Screeplot) (.erp)
- [ ] Convert .erp form EEGLAB to MNE compliant Dataset
- [ ] Split trials into 2 categories : (attended + memorized) VS (ignored)
- [ ] Data dimension structured to be compliant with Python process (initially EEGLAB/MATLAB)

## GOAL (1) Clustering two conditions: Attended vs Ignored
* DATASET: The analyses will use the 10 connectomes (ICA components) power time-frame to decode the 2 modes
* ANALYSE: Train a regression model (or a ML model) to classify trials in 2 groups. 
* Observe / Identify / and Visualize which connectome(s), and during which time-frame is relevant to this attending and memorizing process in working memory.
* Observe the decoding (classification) accuracies and time-frame for decoding it
* --> Find a statistical value publishable and vizualization way

## GOAL (2) Granger Causality analyse on a relevant link
* DATASET: The analyses will use the Hilbert transform data of each channel of relevant link.
* PREPROCESS: Identify a link from a connectome with Beta/Gamma relevant for differentiating the 2 modes
* ANALYSE: Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

## Challenges / to do list
- [ ] Settle the Visual Box + Linux + proper environnement for analyses
- [ ] Find the right architecture / package for cluster analyse
- [ ] Find the right architecture / package for Granger Causality analyse 

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
