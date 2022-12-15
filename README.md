# Signals_Systems
## Frequency Division Multiplexing
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

## Audio Compression
A compressor is an audio tool used to compress the dynamic range of some input source. A compressor works by reducing the level of peaks. The range is reduced, meanwhile the credible loudness of a signal is increased. The loud bits are softened, and the quiet bits are increased in level. 
This project involves a MATLAB-based implementation of an audio compressor. The behavior of the compressor is observed by varying the significant frequency components and observing the trend in the compressed signal. The aim is to retrieve a signal with the minimum signal distortion.
- Read the audio file into MATLAB (Fs=44100 Hz).
- Obtain the frequency spectrum of the audio signal. Plot this frequency spectrum against frequency in Hz.
- Select the first L significant frequency components. Make a vector with the significant frequency components of the signal. This will be the compressed signal. Note that this signal is in the frequency domain.
### NOTE: The lowercase L i.e., ‘l’ is used to denote the first significant frequency components in the code. In our code the variable uppercase L is used to denote the length of Time domain sound vector. Hence for the upcoming the tasks explanations notation of ‘L’ (italics uppercase L) is used for the value of significant frequency components.
- The value ‘L’ selected for frequency components is first divided by 2 since the signal components will be selected from both sides of the spectrum. This was done due to the fact that highest amplitude components of frequencies were present in the middle of frequency spectrum (around origin). 
- Reconstruct the audio signal in time using the compressed signal (which is currently in frequency domain).
- Using this reconstructed frequency spectrum, obtain the audio signal in time domain.
On playing the Audio with value of ‘L’ set to 4000 frequencies, The reconstructed audio is understandable. Apart from some loss of clarity due to compression, It’s still completely comprehensible. Hence it shows that with this value of significant frequencies ‘L’, a good balance between quality and compression is reached.
- Calculate compression ratio
Compression Ratio=100-(Length of significant frequencycomponents)/(Length of orignal signal)*100
### References
1.	https://www.sciencedirect.com/topics/computer-science/frequency-division-multiplexing
2.	https://www.mathworks.com/help/signal/ug/introduction-to-filter-designer.html
3.	https://www.mathworks.com/help/signal/ug/practical-introduction-to-frequency-domain-analysis.html
4.	https://www.mathworks.com/help/signal/ref/thd.html - :~:text=r = thd( x ) returns,length as the input signal
5.	https://academo.org/demos/spectrum-analyzer/
