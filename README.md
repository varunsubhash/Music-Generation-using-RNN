# Music-Generation-using-RNN

The model should be able to generate new music. The input and output are nothing but sequence of musical events. Here the music generated  is restricted to single instrument.

Music can be represented in the below ways.
- Sheet Music -> It contains visual represnetation.
- abc notation -> It is a sequence of letters/alphabets.
- MIDI -> It contains the note/chord to be played and the time stamp at which it should be played.
- MP3 format -> It is a sequence of music sounds.It tells that at a certain frequency and certain amplitude for/at time t.

  In this project, I will be using the abc representation as it is the most simplest notation.
- Abc notation contains metadata and the music.
- The metadata contains information like how to set up the instrument.
- The music contains a sequence of characters.

Here character RNN will be used to generate new music. It is a many to many RNN.
- Character RNN became popular because of the blog by Andrej Karpathy. The link to that blog is mentioned below.
  http://karpathy.github.io/2015/05/21/rnn-effectiveness.
  
- The data for this is obtained from the link => http://abc.sourceforge.net/NMD/.
- To reduce complexity only the jigs file containing 340 tunes will be used.
- The input.text contains the tune and the tunes are concatenated with each other.
- We wll be using batch SGD.
- The total input legth = 129,665.
- It contains 86 unique characters.
- Each character is converted to an index.
- The input is divided into many batches of size 64 X 16.
- The output will conatain a one hot encoded value for the charcater.
- In the model, the input layer will have multpile LSTM layers before the output.
- A character will be fed to the input and the ouput expected will be the next charcater.
- 256 LSTM layers are present between the input and output. Vector of zeros are given as input in the first layer and the subsequent       layers the output of previous LSTM layers are used as input to the preceeding LSTM layer.
- Each LSTM layer is used to learn different things.
- In this model  , return sequences are set to true as we need output as every stage.
- A time distributed layer is constructed at every stage.
- The stateful parameter is set to true as we need the ouput of the first batch to be fed into the next batch.
- This is useful as the model can learn long term dependencies better,
- An embedded layer is also used.
