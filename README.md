# EEG_Connectivity_BrainHack_2019
From scalp EEG data recorded on healthy humans during a visuo-spatial attention task, the project consists in identifying wPLI connectomes that are relevant for encoding a visual stimulus in working memory.
[More about me](https://github.com/anna-monnier)

## Hypotheses and big question
Based on Pascal Fries work on iEEG on monkeys in visual attention field :
* Gamma band phase lock between 2 areas underly a feedforward communication within visual, parietal, and frontal areas.
* Beta phase lock between 2 areas underly a feedback influence
Are there wPLI networks (coupled Beta and Gamma) relevant for attention deployment and encoding in working memory of a visual stimulus ? If yes, what is the relevant time-frame to decode the 2 modes (attended vs ignored) ?

## Aims on connectomes : Clustering 2 conditions (Attended vs Ignored)
* Train a regression model or a machine learning model to classify trials in 2 groupes: (1) trials attended and memorized, (2) trials ignored based on the wPLI (weighted Phase Lag Index) connectomes timelines power. <br/>* 
* Observe / Identify / and Visualize which connectome(s), and during which time-frame is relevant to this attending and memorizing process in working memory.
* train a regression model to discriminate trials with memorizing from those ignoring the stimulus, based on x connectomes time lines.
* Observe the decoding (classification) accuracies and time-frame for decoding it
* FInd a statistica value publishable

## Aims on a link : Granger Causality
* Identify a link from a connectome with Beta/Gamma relevant
* Extract Granger causality value on (1) Gamma band and on (2) Beta band to identify if we corroborate Pascal Fries model of feedforward and feedback influence.

## Dataset
* 50 healthy subjects 
* X trials per subject of 800 msec sampled at 250 Hz
* 14 EEG electrodes - 91 links ?
* Trials segregated based on their caracteristic and bloc

## Tools/Language used
* MATLAB EEGLAB
* Python
