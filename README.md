# RandomForestVoiceActivityDetector

Voice Activity Detection(VAD) distinguishes the speech segments from the non-speech contents in the audio, which is implemented in many speech-related applications such as speech coding, transmission and recognition. This enabling function is also challanged by the complicated auditory environment in the real-world: low signal-noise ratio or various acoustic events in metropolitan environment would interfere with the progress of VAD working. And this project was proprosed for separating the presence of speech from the urban sound evnrionment.

In order to remove the distractions, we could translate this problem to the task of urban Sound Event Detection(SED), which was a common multiclass classification problem. However, ours is relatively easier for the reason of binary classification.(Speech vs. Non-speech) As a result, we could handle this problem by merely using off-the-shelf machine learning frameworks.
