# Digitonicon
This PureData application is a MIDI sequencer based on the sequencer of the Moog Subharmonicon. I created it to use with my Elektron Digitone, hence the name "Digitonicon".


## PureData UI
![digitonicon](https://github.com/user-attachments/assets/1b2fcf47-5293-4bfd-851c-eef0cf39a82a)

The application consists of two 4-note sequences, which send MIDI notes out on channels 1 and 2. There are 4 independent rhythm sub-dividers which can be applied to each sequencer. Multiple rhythms can be applied to the same sequence, allowing you to easily build up complex polyrhythms. The rhythms start at 1: this means play 1 note for every tempo beat. A value of 2 means to play a note every other beat (**_not_** 2 notes per beat). 3 means every third beat, and so on up to 16.

For more information, you should look into the Subharmonicon's sequencer.


## MIDI Out
The application outputs MIDI notes on channel 1 for sequencer 1, and channel 2 for sequencer 2. The `Note Length` sliders determine how many milliseconds a MIDI note is on for.


## MIDI In
Every part of the application can be controlled with MIDI. I configured it to be easily controllable with a Digitone synthesizer, which can be used as a MIDI controller for external software and hardware. Generally, sequencer 1 is controlled with channel 1, and sequencer 2 with channel 2, though common functionality is spread across both channels.

### MIDI CC
| MIDI CC | Channel | Function |
| --- | --- | --- |
| 70, 71, 72, 73 | 1, 2 | Set the MIDI note values for each sequencer |
| 74, 75, 76, 77 | 1 | Set the length of the four rhythm sliders |
| 74, 75, 76 | 2 | Set the tempo with three levels of granularity |
| 1 | 1, 2 | (Mod wheel) Set the MIDi note length for each sequencer |


### MIDI Notes
Specific MIDI notes are also used as buttons. 
On the Digitone, I set the octave to -5 and set the keyboard to chromatic with KB folding on. This allows all note buttons to be used without changing octaves.

| MIDI Note |  Channel | Function |
| --- | --- | --- |
| 0 | any | Reset the sequencers |
| 8, 9, 10, 11 | 1, 2 | Assign a rhythm divider to a sequencer |
| 15 | 1, 2 | Go to the next note in the sequence |


### Transport Control
If you set up the Digitone to send transport data, you can use the start/stop buttons to start and stop the sequencer. The app does not distinguish between start and stop, so both buttons can be used interchangeably.


