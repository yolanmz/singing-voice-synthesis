# INTRODUCTION

Human voice is a complex signal since it is made of many small and random variations produced by air passing through the vocal folds. As a result, it could be challenging to make it sound natural. I am interested in how natural singing voice can be simulated, so this project is an exploration of singing voice synthesis. With the sound synthesis techniques I have learned in MUMT307, I built a Max Patcher generating human singing vowels.

# DESIGN & METHOD

The model applied in this patcher is based on the methods proposed by Belánger, Traube and Piché in *Designing and Controlling a Source-filter Model For Naturalistic and Expressive Singing Voice Synthesis*[1]. The two most important elements for our model are the sound source and the filter.
## Sound Source
Belánger, Traube and Piché proposed that the excitation signal should be a mix of an impulse train generator and a noise generator, in order to produce a harmonic and noisy signal[1]. They also suggested using a filtered pink noise with a very low amplitude multiplied with the impulse train generator to simulate sound roughness, known as the noise caused by burst turbulence when air passes from the lungs through the vocal folds. There are also examples on using a scaled sinusoid as the source signal[2]. Therefore, I included three options for the harmonic source signal in the patcher: an impulse train, an impulse train including roughness and a scaled sinusoid. A noise signal is added to all of them to simulate breath.
## Filter
Each vowel is made of five formants defined in the the international phonetic alphabet. A formant is a local maximum in the spectrum. Each formant serves as a bandpass filter in parallel with each other to form the filter simulating vocal tract. The first two formants are crucial for the vowel sounds. The third and fourth formants are used for the perception and categorization of the consonants and the fifth formant contributes to the tone quality. <br />
Here is a vowel chart including the first and second formant frequencies. 
![vowelChart](media/vowel_chart.jpeg)[3]<br />
From the chart, we can see that the first formant usually falls under 1000 hertz and the second formant falls between 500 to 3000 hertz. These two formants are enough to identify a vowel. <br />
In this project, we synthesize the vowels with the formant frequencies from this chart below. All five formant frequencies are given here. The user has the option to choose between filter of three formants or filter of five formants to compare the sound quality difference.
![formantFrequencies](media/formant_frequencies.png) <br />
## Other Module
Some other parameters are introduced to add variations to the resulting sound.
### Vibrato
A vibrato is included in the patcher in order to achieve a more natural sound effect. According to Belánger, Traube and Piché, a deviation of about 1% of the fundamental frequency results in the most natural sounding human voice[1]. The ideal vibrato rate should be within the range of 5-8 Hz.
### Pitch shifter
I also included a pitch shifter in this patcher. Initially, I looked up formant frequencies of female singing voice and child's singing voice and hoped to synthesize voice of different characters. However, they all end up sounding like the male voice. Since women and children speak a higher pitch than men in general, I added an option to pass the resulting sound to a pitch shifter and expected it would make a difference. 
# USAGE
Here is a screenshot of the user interface. <br />
![maxPatcher](media/patcher.png)

# CHALLENGE

# CONCLUSION

# REFERENCE
