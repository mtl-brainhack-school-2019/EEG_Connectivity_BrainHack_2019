# EEG_Connectivity_BrainHack_2019
* RawData: Scalp EEG data - Biosemi - 250 Hz - 64 electrodes
* Subjects: 50 healthy humans 
* Task: Visuo-spatial attention task (x trials per Main condition)
* The project consists in identifying wPLI connectomes that are relevant for encoding a visual stimulus in working memory.
* [Poster of the project](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/Anne_Monnier_OHBM_Connectomes.pdf "Poster")
* [Fries](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/blob/master/pascal_fries.jpg "Fries")

## Pre-processed Data
- [X] On continuous signal, blinks and artefacts filtered + scalp current density (avoid volume conduction)
- [X] 14 electrodes selectionned: Beta and Gamma filtered and Hilbert transform applied
- [X] On 91 links, wPLI calculated for each band, then epoched on 800 ms. 
- [X] PCA/ICA applied on beta and Gamma wPLI for 10 components (Screeplot).
- [ ] Trials split into 2 categories : attended and ignored
- [ ] Data dimension structured to be compliant with Python process (initially EEGLAB/MATLAB)

## GOAL (1) Clustering two conditions based on connectomes: Attended vs Ignored
* The analyses will use the 10 components time-frame to decode the 2 modes
* Train a regression model or a machine learning model to classify trials in 2 groupes: (1) trials attended and memorized, (2) trials ignored based on the 10 wPLI (weighted Phase Lag Index) connectomes timelines power. <br/> 
* Observe / Identify / and Visualize which connectome(s), and during which time-frame is relevant to this attending and memorizing process in working memory.
* train a regression model to discriminate trials with memorizing from those ignoring the stimulus, based on x connectomes time lines.
* Observe the decoding (classification) accuracies and time-frame for decoding it
* FInd a statistica value publishable

## GOAL (2) Granger Causality analyse on a relevant link
* The analyses will use the Hilbert transform data of each channel of relevant link.
* Identify a link from a connectome with Beta/Gamma relevant for differentiating the 2 modes
* Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

## Challenges / to do list
- [ ] Settle the Visual Box + Linux + proper environnement for analyses
- [ ] Find the right architecture / package for cluster analyses 
- [ ] Find the right architecture / package for cluster analyses 

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

