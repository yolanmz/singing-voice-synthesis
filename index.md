# INTRODUCTION

Human voice is a complex signal since it is made of many small and random variations produced by air passing through the vocal folds. As a result, it could be challenging to make it sound natural. I am interested in how natural singing voice can be simulated, so this project is an exploration of singing voice synthesis. With the sound synthesis techniques I have learned in MUMT307, I built a Max Patcher generating human singing vowels.

# Design & Method

The two most important elements for our model are the sound source and the filter.
## Sound Source
Belánger, Traube and Piché proposed that the excitation signal should be a mix of an impulse train generator and a noise generator to produce a harmonic and noisy signal[1].
## Filter
Each vowel is made of five formants defined in the the international phonetic alphabet. A formant is a local maximum in the spectrum.
Each formant serves as a bandpass filter in parallel with each other to form the filter simulating vocal tract.
# Reference
