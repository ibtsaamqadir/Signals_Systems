# Signals_Systems
##1. Frequency Division Multiplexing
Frequency-division multiplexing (FDM) is a technique, used in telecommunications, that divides the overall bandwidth available in a communication channel into a number of non-overlapping frequency bands, each of which carries a distinct signal.
To perform Frequency Division Multiplexing (FDM), several steps are followed:
- Record the audion signals.
- After gathering the audio signals, a low pass filter was designed using FDA Tool (Filter Design and Analysis Tool), for which the cutoff frequency was 3k Hertz.
- After designing the Low Pass Filter of 3k frequency, all the audios were passed from the designed filter. The function audioLowpass3k() was called to carry out the filtering of all the audio signals.
- After passing all the audio signals from the filter, each filtered audio signal was modulated.
- The function of modulation() was called to perform modulation. The function takes the filtered audio signal, frequency for modulation and time as inputs.
- After modulating all the four signals with the frequencies as mentioned above, all the four signals were added to obtain a single multiplexed signal. The function add4Signals() was used. 
- Four separate bandpass filters were designed for the frequencies 3k, 9k, 15k and 21k using FDA tool in MATLAB. The bandwidth was determined by analyzing the spectrum of multiplexed signal in frequency domain. 
- After designing these bandpass filters, the sum was passed through the bandpass filter to obtain the respective signal. The function bandpass()  was used for this purpose, which takes only the multiplexed signal as the input and returned four signals. 
- After getting the respective impulse responses, the signals were again modulated with the respective frequencies, Mariam.mp3 with 3k, Ibtsaam.mp3 with 9k, adeel.mp3 with 15k and nazeefa.mp3 with 21k. Again, modulation() was used. 
- Again the modulated signals were passed through the low pass filter. 3k low pass filter looked optimum to retrieve the original signals. We used again the audioLowpass3k() function again. 
- The signals were converted to audios using audiowrite() function of the MATLAB.
- The main() function in which every other function is called. To execute the complete program, write main in the command window. 
