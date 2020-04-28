# Music-Generation-using-RNN

The model should be able to generate new music. The input and output are nothing but sequence of musical events. Here the music generated  is restricted to single instrument.

Music can be represented in the below ways.
- Sheet Music -> It contains visual represnetation.
- abc notation -> It is a sequence of letters/alphabets.
- MIDI -> It contains the note/chord to be played and the time stamp at which it should be played.
- MP3 format -> It is a sequence of music sounds.It tells that at a certain frequency and certain amplitude for/at time t.

- In this project, I will be using the abc representation as it is the most simplest notation.
- Abc notation contains metadata and the music.
- The metadata contains information like how to set up the instrument.
- The music contains a sequence of characters.

