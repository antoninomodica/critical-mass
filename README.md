# critical-mass

## About
Critical Mass is a surround granular synthesizer based on the Boids flocking algorithm originally developed by Craig Reynolds. The audio engine is implemented in the visual programming language Max/MSP, while swarming functionalities are based on JavaScript. Every grain of sound is represented by a sound particle moving in space; the 32 voices of the synthesizer together create an organic cloud of particles. The aim of the project is the tight integration between the characteristics of the particle swarm and the parameters of the granular synth, creating a responsive musical instrument.

## Dependencies
- full installation of Max 8. Download from https://cycling74.com/downloads
- external objects library **spat** by IRCAM. Download https://forum.ircam.fr/projects/detail/spat/

## Usage
### Starting the software
After installing the latest version of Max and Spat, double click on the file corresponding to the desired type of output (either binaural or 8-channel).

### File Selection and Presets
Files can be selected either via the "Select folder" button and dropdown menu combination, or by dragging and dropping. By highlighting a slice of the waveform it is possible to choose which section of the file is going to be used for the sound generation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115150374-518a6780-a068-11eb-84ad-ce08fedc87f2.png" alt="file_selection"/>
</p>

### Engines
Once the desired file is selected, both the **synth** and the **flocking** engines can be started via the dedicated switches. As soon as the flocking switch is turned on, the window on the right is automatically populated with 32 particles flying around.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115150469-d4abbd80-a068-11eb-805e-4d044b723049.png" alt="engine_switches"/>
</p>

From here, the **Doppler** and **Gravity** functionalities can also be activated.
When **Doppler** is active, a doppler effect simulation is applied to all particles, making the pitch of the corresponding sound grain be affected by its movement speed.
When **Gravity** is active, a small circle appears on the visualization window on the right. By clicking on the window it is possible to define a gravitational point around which the particles will start swarming.


### Control
The control area contains the main parameters of the synthesizer and swarm. Most of the controls exposed to the user are related to the parameters of the sound engine. All of the parameters have a center value and a randomness value expressed in %. By changing the randomness amount the corresponding value will randomly oscillate around the chosen center value with the desired variance.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115150540-218f9400-a069-11eb-83db-7c4d2bc82ff8.png" alt="control_window"/>
</p>


The currently exposed parameters are:

- **Duration**: length of the grains, in milliseconds
- **Pitch**: playback rate of the grains, with 1 corresponding to original pitch
- **Amp**: amplitude of the grains, 0 to 1. (the maximum value is hardcoded to 0.8 to prevent overcrowding the audio bus with 32 voices)
- **Velocity**: maximum value for the velocity of the grains (between 0.3 and 0.8)
- **Size**: size ratio of the virutal room in which the listener is placed, from 1:1 up until 10:1. Bigger sizes involve particles flying around at higher speed.


## Mapping

Currently the mapping between parameters is hardcoded. The idea is to keep the mappings relatively hidden to the end user, with the aim of creating organic and responsive behaviors. The current mapping includes:
- Grain duration -> Separation threshold <br/>
  Longer sound grains will influence the flocking algorithm by increasing the minimum distance between the particles. This means that when longer sounds are generated they are also further apart from each other, leaving more space for sound to exist in space.
- Velocity -> Inertia <br/>
  When the particles are moving at faster velocity, their inertia is also reduced, making them stick together more easily. In this way it is possible, with just one control, to smoothly transition between a localized mass of sound to a more evenly distributed particle arrangement.
  
  
