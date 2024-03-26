<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

VegaSynth is a small synthesizer for Tiny Tapeout. The design goals are as follows:
- 4+ channels
- In tune over 32Hz to 2kHz
- Volume control
- Brightness control
- Multiple waves (saw, square, noise...)
- Detune or PWM effect
- Simple stereo

Due to the small number of cells available, this requires a special design.

## How to test

VegaSynth accepts commands in the form of extremely basic MIDI:
- 8n xx yy: Turn off channel n. (xx must match current note)
- 9n xx yy: Turn on channel n (if off) and update its note to xx and its volume to yy. (both 0..127)
- Bn 07 yy: Set channel n volume. (0..127; this overwrites velocity)
- Bn 0A yy: Set channel n pan. (0..127; 8 values, low 4 bits ignored)
- Bn 4A yy: Set channel n brightness. (0..127)
- Bn 5E yy: Set channel n detune/PWM effect depth. (0..127)
- Bn 7B yy: Turn off channel n. (MIDI all notes off)
- Cn xx: Set channel n waveform.
- En xx yy: Pitch bend channel n by yy. (0..127 = -2 to +1.96875 semitones, LSB ignored)

## External hardware

VegaSynth requires an external CPU to play music.

It is recommended to use software modulation for the following features:
- Volume envelope
- Brightness envelope
- Vibrato
- Assignable LFO
- Assignable envelope
