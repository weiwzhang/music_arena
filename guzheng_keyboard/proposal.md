# Guzheng Keyboard
(Guzheng: a Chinese traditional instrument)

## Overview:  
Guzheng Keyboard allows you to use just a simple computer keyboard to try out different Guzheng sounds, and accompany these sounds with some background music too. I’ve been playing Guzheng for 10+ years now and I love it deeply. I've always wanted to have a handy tool that can easily demonstrate Guzheng timbre and simple techniques, and also help integrate the acoustic Guzheng sounds into the digital world. So I developed this project.

## Development:
My biggest lesson learned from working on this project (and also through this course) about making music is don’t be afraid to experiment with the unknown! A lot of the sound synthesis here are definitely due to accidental experimentations, and I love them! The following are main concepts used in my work:
1. Keyboard modes: I started out having a vague idea of making a keyboard instrument that somehow plays Guzheng sounds (sound snippets of individual notes or specific techniques from my own Guzheng recordings). I used a delegation model to play the samples. Then to make the single Guzheng voice more interesting, I added two different sound effects.
      1. Delegations: the sub-patcher note_delegator delegates g_notes to play Guzheng samples as dictated by keyboard inputs.
      1. Delays: using tapin and tapout, I can add a sustaining (or granular) effect on the sounds I’m playing live (like a dampering pedal on piano).
      1. Modulation synthesis: this is a beautiful accident. I did modulation synthesis while playing live samples, and to my surprise, I produced a sound that’s very similar to Chinese zither, which is the ancestor instrument of Guzheng. 
1. Background music synthesis:
      1. Phase~, counter, function tables: I was able to produce a simple, repetitive drum beat by walking through function tables to pick certain samples and play them at different amplitudes. 
      1. Dynamic Resonators: I used resonators and made my models by cherry-picking higher-range and lower-range frequencies I really liked from moonlight_intro sound file. Then I made them evolve dynamically using cycle~.

## Future Improvement:
I think the dynamic of resonators can change more or contrast more. Right now they have some variations but can be improved. In addition, I would like to experiment more with how to structure the amplitude dynamics of my keyboard Guzheng sound and background music, to make them more harmonic or inharmonic.   
