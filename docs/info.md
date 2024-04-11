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

VegaSynth accepts 16-bit commands to set these settings (where n is the channel number and vv is the value):
- n2vv: Pitch A LSB
- n3vv: Pitch A HSB
- n4vv: Wave A
- n5vv: Osc A/B combine mode and sync
- n6vv: Slew rate up
- n7vv: Slew rate down
- n8vv: Volume
- n9vv: Panning
- nAvv: Pitch B LSB
- nBvv: Pitch B HSB
- nCvv: Wave B

## External hardware

VegaSynth requires an external CPU to play music.

It is recommended to use software modulation for the following features:
- Volume envelope
- Brightness envelope
- Vibrato
- Assignable LFO
- Assignable envelope
