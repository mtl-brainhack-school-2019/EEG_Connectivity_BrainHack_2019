# EEG_Connectivity_BrainHack_2019
* Dataset: Scalp EEG data 
* Subjects: 50 healthy humans 
* Task: Visuo-spatial attention task (x trials per Main condition)
* The project consists in identifying wPLI connectomes that are relevant for encoding a visual stimulus in working memory.
[More about me](https://github.com/anna-monnier)
[More about the project](github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/poster.jpg "Poster")

## Hypotheses and big question
![Feedforward and Feedback influence - Pascal Fries ](https://github.com/mtl-brainhack-school-2019/EEG_Connectivity_BrainHack_2019/pascal_fries.jpg "pascal_Fries")
Based on Pascal Fries work on iEEG on monkeys in visual attention field :
* Gamma band phase lock between 2 areas underly a feedforward communication within visual, parietal, and frontal areas.
* Beta phase lock between 2 areas underly a feedback influence
* At a large scale, what are the wPLI networks (coupled Beta and Gamma) relevant for attention deployment and encoding in working memory of a visual stimulus ? 
* What is the relevant time-frame to decode the 2 modes (attended vs ignored) based on these connectomes ?

## Raw Data
* Bio-semi 250 Hz 64 electrodes

## Pre-processed Data
* On continuous signal, blinks and artefacts filtered + scalp current density (avoid volume conduction)
* 14 electrodes selectionned: Beta and Gamma filtered and Hilbert transform applied
* On 91 links, wPLI calculated for each band, then epoched on 800 ms. 
* PCA/ICA applied on beta and Gamma wPLI for 10 components (Screeplot).
* The analyses will use the 10 components time-frame to decode the 2 modes

## (1) Clustering 2 conditions (Attended vs Ignored) based on connectomes
Aim of the study:
* Train a regression model or a machine learning model to classify trials in 2 groupes: (1) trials attended and memorized, (2) trials ignored based on the wPLI (weighted Phase Lag Index) connectomes timelines power. <br/>* 
* Observe / Identify / and Visualize which connectome(s), and during which time-frame is relevant to this attending and memorizing process in working memory.
* train a regression model to discriminate trials with memorizing from those ignoring the stimulus, based on x connectomes time lines.
* Observe the decoding (classification) accuracies and time-frame for decoding it
* FInd a statistica value publishable

## (2) Granger Causality analyse on a relevant link
Aim of the study:
* Identify a link from a connectome with Beta/Gamma relevant for differentiating the 2 modes
* Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

## Challenges and to do list
* Check Bids standards for EEG sharing data
* MATLAB / EEGLAB based data: Transform data in Python compliant
* Settle a proper environnement for analyses
* Find the right package for Granger Causality


