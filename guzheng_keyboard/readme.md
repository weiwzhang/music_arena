# Guzheng Keyboard
(Ableton Max 7, UC Berkeley music research language o.)

## Overview:  
Guzheng Keyboard is a small digital instrument that allows you to use just a simple computer keyboard to try out different Guzheng (a Chinese traditional instrument) sounds, and accompany these sounds with some background music too. I’ve been playing Guzheng for 10+ years now and I love it deeply. I've always wanted to have a handy tool that can easily demonstrate Guzheng timbre and simple techniques, and also help integrate the acoustic Guzheng sounds into the digital world. So I developed this project.

## Setup:
You will need Max 7 to open and edit the files (patchers). See installation instructions here: https://cycling74.com/shop. To download odot and other Berkeley-develeped Max externals, please go to UC Berkeley CNMAT website: http://cnmat.berkeley.edu/downloads (see CNMAT Max Externals and CNMAT odot externals). It's recommended to put your Max 7 folder in your `Documents` (for Mac) or `My Documents` (for Windows) directory, and put CNMAT odot folder and CNMAT Max Externals folder in `Max 7/Packages` directory.      

(An important note: to make sure Max7 is able to play media files, odot and externals, add these folder paths in your Max. See instructions for Max 7 on how to do so.)

## Development:
The main patcher (`guzheng_keyboard.maxpat`) consists of two parts: the keyboard modes, which allows users to play different Guzheng sound samples (simple notes and some techniques pre-recorded on an actual Guzheng instrument) by typing on the computer keyboard, and the background music (synthesis of some sound snippets to create a simple drum beat and other sound effects). Each part can be played individually, or you can try playing them together and see the effects. `guzheng_keyboard_demo.aif` is a short sound snippet demonstrating this digital instrument. 

The following are main concepts used in my work:    
(note: components referred to here are Max 7 objects)
1. In Keyboard Modes section: I used a delegation model to play the Guzheng sound samples. Then to make the single Guzheng voice more interesting, I added two different sound effects.
      1. Delegations: the sub-patcher note_delegator delegates g_notes to play Guzheng samples as dictated by keyboard inputs.
      1. Delays: using tapin and tapout, I can add a sustaining (or granular) effect on the sounds I’m playing live (like a dampering pedal on piano).
      1. Modulation synthesis: this is a beautiful accident. I did modulation synthesis while playing samples live, and to my surprise, I produced a sound that’s very similar to Chinese zither, which is the ancestor instrument of Guzheng. 
1. In Background Music section:
      1. Phase~, counter, function tables: I was able to produce a simple, repetitive drum beat by walking through function tables to pick certain samples and play them at different amplitudes. 
      1. Dynamic Resonators: I used resonators and made my models by cherry-picking higher-range and lower-range frequencies I really liked from moonlight_intro sound file. Then I made them evolve dynamically using cycle~.

## Future Improvement:
I think the dynamic of resonators can change more or contrast more. Right now they have some variations but can be improved. In addition, I would like to experiment more with how to structure the amplitude dynamics of my keyboard Guzheng sound and background music, to make them more harmonic or inharmonic.       

My biggest lesson learned from working on this project about making music is don’t be afraid to experiment with the unknown! A lot of the sound synthesis here are definitely due to accidental experimentations, and I love them! 

