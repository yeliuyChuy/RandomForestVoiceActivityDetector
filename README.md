# RandomForestVoiceActivityDetector

Voice Activity Detection(VAD) distinguishes the speech segments from the non-speech contents in the audio, which is implemented in many speech-related applications such as speech coding, transmission and recognition. This enabling function is also challanged by the complicated auditory environment in the real-world: low signal-noise ratio or various acoustic events in metropolitan environment would interfere with the progress of VAD working. And this project was proprosed for separating the presence of speech from the urban sound evnrionment.

In order to remove the distractions, we could translate this problem to the task of urban Sound Event Detection(SED), which was a common multiclass classification problem. However, ours is relatively easier for the reason of binary classification.(Speech vs. Non-speech) As a result, we could handle this problem by merely using off-the-shelf machine learning frameworks.

## Table of Contents

- [Install](#install)

## Install

1. In case of no data set available, some data and tools offered here for synthesizing urban soundscape data:
- [UrbanSound8K](https://urbansounddataset.weebly.com/urbansound8k.html) by [@justinsalamon](https://github.com/justinsalamon), which contains 8732 labeled sound excerpts (<=4s) of urban sounds from 10 classes: air_conditioner, car_horn, children_playing, dog_bark, drilling, enginge_idling, gun_shot, jackhammer, siren, and street_music.
- [Mozilla Common Voice](https://voice.mozilla.org/en), a crowdsourcing project started by Mozilla to create a free database for speech recognition software.
- [scaper](https://github.com/justinsalamon/scaper) by [@justinsalamon](https://github.com/justinsalamon), A library for soundscape synthesis and augmentation.
- [UrbanSound-SED](http://urbansed.weebly.com/) by [@justinsalamon](https://github.com/justinsalamon),a example dataset of 10,000 synthetic soundscapes with sound event annotations generated using scaper
