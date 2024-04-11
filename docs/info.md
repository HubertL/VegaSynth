<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

VegaSynth is a small synthesizer for Tiny Tapeout. Here are the specs:
- 8 channels
- Each channel contains 2 pulse wave / noise oscillators
- Selectable oscillator combination
- Osc sync
- Volume control
- Slew rate limiter (controls brightness); separate rate for up/down allows for saw waves
- Simple stereo (left/mid/right)

## How to test

VegaSynth accepts commands to set these settings (where n is the channel number):
- n2: Pitch A LSB
- n3: Pitch A HSB
- n4: Wave A
- n5: Osc A/B combine mode and sync
- n6: Panning
- n7: Volume
- nA: Pitch B LSB
- nB: Pitch B HSB
- nC: Wave B
- nE: Slew rate up
- nF: Slew rate down

## External hardware

VegaSynth requires an external CPU to play music.

It is recommended to use software modulation for the following features:
- Volume envelope
- Brightness envelope
- Vibrato
- Assignable LFO
- Assignable envelope
