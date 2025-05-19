🎸 Transformer Music Generator (Guitar MIDI)
This project implements a Transformer-based music generation model for creating guitar-like MIDI sequences. It tokenizes musical notes based on pitch and duration, trains a model on MIDI input, and generates new sequences.

🧠 What It Does
Converts MIDI note sequences into tokens for model training

Uses a Transformer neural network to learn musical patterns

Trains on tokenized sequences to predict the next note

Can generate new music by sampling from the model's predictions

Converts generated tokens back to MIDI for playback

🎼 How It Works
🔁 Tokenization
Notes are represented as (pitch, duration) pairs. These are converted into integer tokens using:

Pitches: From MIDI note 40 (E2) to 88 (F6), giving 49 pitch tokens

Durations: Quantized into 6 types (e.g. 1/8 note, 1/4 note, 1/2 note, etc.)

🧪 Sequence Creation
Sequences of tokens are chopped into overlapping input-output pairs for training

Each input is a fixed-length sequence of tokens

The target is the next token in the sequence

🧱 Model Architecture
A simple Transformer model with:

Embedding layers for tokens and positions

A single multi-head attention block

Feedforward layers and dropout for regularization

Final softmax layer over vocabulary

🏋️‍♂️ Training
Model is trained using sparse_categorical_crossentropy loss and the Adam optimizer.

🎵 Generation
Given a seed sequence, the model can generate new music using temperature-controlled sampling.

🔄 MIDI Output
The token sequence is converted back to a playable MIDI file using pretty_midi.


