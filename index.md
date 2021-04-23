# INTRODUCTION

Human voice is a complex signal since it is made of many small and random variations produced by air passing through the vocal folds. As a result, it could be challenging to make it sound natural. I am interested in how natural singing voice can be simulated, so this project is an exploration of singing voice synthesis. With the sound synthesis techniques I have learned in MUMT307, I built a Max Patcher generating human singing vowels.

# Design & Method

The two most important elements for our model are the sound source and the filter.
## Sound Source
Belánger, Traube and Piché proposed that the excitation signal should be a mix of an impulse train generator and a noise generator, in order to produce a harmonic and noisy signal[1]. They also suggested using a filtered pink noise with a very low amplitude multiplied with the impulse train generator to simulate sound roughness, known as the noise caused by burse turbulence when air passes from the lungs through the vocal folds. 
## Filter
Each vowel is made of five formants defined in the the international phonetic alphabet. A formant is a local maximum in the spectrum.
Each formant serves as a bandpass filter in parallel with each other to form the filter simulating vocal tract. The first two formants are crucial for the vowel sounds. The third and fourth formants are used for the perception and categorization of the consonants and the fifth formant contributes to the tone quality. <br />
Here is a vowel chart including the first and second formant frequencies. 
![vowelChart](media/vowel_chart.jpeg)<br />
From the chart, we can see that the first formant usually falls under 1000 hertz and the second formant falls between 500 to 3000 hertz. These two formants are enough to identify a vowel. <br />
![formantFrequencies](media/formant_frequencies.png)<br />
In this project, we synthesize the vowels with the formant frequencies from this chart above.
## Other Module
### Vibrato
### Pitch shifter

# Usage

# Challenge

# Future Improvement

# Reference
