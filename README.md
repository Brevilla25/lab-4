# lab-4

#Part 2 

1. What are the different bit resolutions can you set the ADC? What is the maximum sampling
rate at each of these resolutions? Where did you find this information in the datasheet?

- supports 12, 10, 8, and 6-bit resolution (pg. 705 reference manual). Conversion time is T-SMPL + T-SAR(p. 636), with T_SAR = 12.5, 10.5, 8.5, and 6.5 cycles (p. 652) 

3. Why do you need a voltage divider circuit? What would happen if the photodiode is directly
connected to the board?
The LDRs resistance changes with exposure to light, the ADC measures voltage not resistance so it can't read that directly. So, you use a voltage divider to turn this resistance into voltage, as the LDRs resistance changes the value you get for Vout changes with it and the ADC can now read it. If the photodiode was just connected to the board, since it just sits between 3v3 and the ADC pin there wouldn't be anything to set the voltage, it would just sit at 3v3 or float despite the amount of light being exposed. 


#Part 3
 3.  If B = 9, what is Vout? Express your answer in terms of Vref . Use the DAC mode that
provides the best resolution available on your MCU (refer to the data sheet).

4. How does the sampling rate of the DAC affect the quality of the output waveform? What
are the differences in sound perception between sine, square, and sawtooth waves? Why do we need a
capacitor in the signal path when sending an audio signal to a speaker or earphones?

(Im so sorry I wasn't able to get a video, I was already on the plane when I was working on part 3 and forgot I needed an oscilliscope :(, the people on the plane had a laugh at me though when I brought out the MCU and breadboard on my tiny airplane desk (look at my extra photo :D). LOL )




#Part 4

