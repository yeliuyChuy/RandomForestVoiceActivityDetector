# RandomForestVoiceActivityDetector

Voice Activity Detection(VAD) distinguishes the speech segments from the non-speech contents in the audio, which is implemented in many speech-related applications such as speech coding, transmission and recognition. This enabling function is also challanged by the complicated auditory environment in the real-world: low signal-noise ratio or various acoustic events in metropolitan environment would interfere with the progress of VAD working. And this project was proprosed for separating the presence of speech from the urban sound evnrionment.

In order to remove the distractions, we could translate this problem to the task of urban Sound Event Detection(SED), which was a common multiclass classification problem. However, ours is relatively easier for the reason of binary classification.(Speech vs. Non-speech) As a result, we could handle this problem by merely using off-the-shelf machine learning frameworks.

This project consists of 5 stages as:
0. Soundscape generation
1. Feature extraction
2. Model selection
3. Data Augmentation
4. Decision Smoothing

Step.0 was performed due to the lack of the off-the-shelf data set, in which the [UrbanSound8K](https://urbansounddataset.weebly.com/urbansound8k.html) and [Mozilla Common Voice](https://voice.mozilla.org/en) were used to create our synthetic urban soundscape data.

Step.1 is the frontend processing that turns raw audio data into concise but logical representation. In this research, the Per-Channel Energy Normalization(PCEN)([Wang et al., 2017](https://arxiv.org/pdf/1607.05666.pdf),[Lostanlen
et al., 2018](http://www.justinsalamon.com/uploads/4/3/9/4/4394963/lostanlen_pcen_spl2018.pdf) was tested with a promising result even better than Mel Frequency Cepstral Coefficents (MFCCs), especially in the condition of low signal-noise-ratio(SNR).

Step.2 is the procedure of selecting a statistical model. Since we've already determined to used Random Forest Classifier, this step only contains metric selection, hyperparameter optimization through grid-search cross-validation.

Step.3 is for improving the robustness of our model by fitting the model to more degraded data and evaluated on the unmodified example. For audio-related data augmentation, deformations such as pitch shift, time stretch, colored noise, dynamic range compression, and IR convolution would effective and their open-source implementations are available in [muda](https://github.com/bmcfee/muda)

Step.4 models the occurrence of speech and non-speech by Hidden-Markov-Model, and find its most likely states sequence through Viterbi Decoding in order to smooth the snatchy decisions by classifier.

## Table of Contents

- [Optional Dataset](#Optional Dataset)
- [Install](#install)

## Optional Dataset

- In case of no data set available, some data sets and tools offered here for synthesizing urban soundscape data:
    - [UrbanSound8K](https://urbansounddataset.weebly.com/urbansound8k.html) by [@justinsalamon](https://github.com/justinsalamon), which contains 8732 labeled sound excerpts (<=4s) of urban sounds from 10 classes: air_conditioner, car_horn, children_playing, dog_bark, drilling, enginge_idling, gun_shot, jackhammer, siren, and street_music.
    - [Mozilla Common Voice](https://voice.mozilla.org/en), a crowdsourcing project started by Mozilla to create a free database for speech recognition software.
    - [scaper](https://github.com/justinsalamon/scaper) by [@justinsalamon](https://github.com/justinsalamon), A library for soundscape synthesis and augmentation.
    - [UrbanSound-SED](http://urbansed.weebly.com/) by [@justinsalamon](https://github.com/justinsalamon),a example dataset of 10,000 synthetic soundscapes with sound event annotations generated using scaper
    - [SONYC Urban Sound Tagging (SONYC-UST)](https://zenodo.org/record/2590742#.Xg5ZqtZKjFQ), a dataset for the development and evaluation of machine listening systems for realistic urban noise monitoring. 
