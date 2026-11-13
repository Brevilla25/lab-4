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

- Vout = (B / 2ⁿ) × Vref, DAC can use an 8-bit or a 12-bit, 12-bit is the better resolution, so
- n = 12, 2^12 = 4096 codes
- Vout = (9 / 4096) × Vref
       = 0.0022*Vref
  

4. How does the sampling rate of the DAC affect the quality of the output waveform? What
are the differences in sound perception between sine, square, and sawtooth waves? Why do we need a
capacitor in the signal path when sending an audio signal to a speaker or earphones?
- The DAC output is made from N samples per cycle, and the sample rate is: fsample = fsine × N. Choosing N = 32, want 262 Hz(middle c) × 32 = 8384 samples per second. If we have more samples per cycle, this gives us smaller steps, which gives us a smoother wave closer to a sine and little distortion (better quality). Looking at Nyquist rule from L7, the sample rate has to exceed twice the highest frequency we want, so if we had a low rate in comparison to the tone, it would give us a distorted wave. 
The differences: 
- For a sine wave it sounds very smooth and clean
- For a square wave, you get the basic sound/wave with the addition of the odd harmonics (3rd, 5th, 7th), more hollow sounding.
- And for a sawtooth, you get the basic sound/wave with the addition of all the harmonics (both odd and even). It sounds very bright and brassy..

- You need a capacitor since the DAC output only goes between 0 and 3.3 V, it carries a DC offset on top of the sine wave. The capacitor blocks the extra DC and passes only the changing (AC) part (a high-pass filter). Since we are using headphones/ speaker/earphones), these devices are a coil, and a constant DC voltage pushes a steady current through it and holds it off to one side, meaning it can’t move freely with the signal.
  
(ALSO Im so sorry I wasn't able to get a video, I was already on the plane when I was working on part 3 and forgot I needed an oscilliscope :(, the people on the plane had a laugh at me though when I brought out the MCU and breadboard on my tiny airplane desk (look at my extra photo :D). LOL )




#Part 4
code + video(link to Google Drive) uploaded
