# critical-mass

## About
CriticalMass is a surround granular synthesizer based on the Boids flocking algorithm originally developed by Craig Reynolds. The audio engine is implemented in the visual programming language Max/MSP, while swarming functionalities are based on JavaScript. Every grain of sound is represented by a sound particle moving in space; the 32 voices of the synthesizer together create an organic cloud of particles. The aim of the project is the tight integration between the characteristics of the particle swarm and the parameters of the granular synth, creating a responsive musical instrument.

## Dependencies
- full installation of Max 8. Download from https://cycling74.com/downloads
- external objects library **spat** by IRCAM. Download https://forum.ircam.fr/projects/detail/spat/

## Usage
### File Selection
In the top section of the main view it is possible to pick a folder containing the samples to be used in the synth. When a file is selected via the dropdown menu, its waveform is visualized right underneath it. By highlighting a slice of the waveform it is possible to choose which section of the file is going to be used for the sound generation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115115647-dc4e6200-9f95-11eb-8548-088af402eef6.png" alt="file_selection"/>
</p>

### Engines
Once the desired file is selected, both the **sound** and the **flocking** engines can be started via the dedicated switches. As soon as the flocking switch is turned on, the window on the right is automatically populated with 32 particles flying around.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115115704-16b7ff00-9f96-11eb-96d3-ffaf5294e12a.png" alt="engine_switches"/>
</p>


### Control
The control area contains the main parameters of the synthesizer and swarm. Most of the controls exposed to the user are related to the parameters of the sound engine. All of the parameters have a center value and a randomness value expressed in %. By changing the randomness amount the corresponding value will randomly oscillate around the chosen center value with the desired variance.

<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115116020-cb065500-9f97-11eb-8b86-e72a3ee04528.png" alt="control_window"/>
</p>

The currently exposed parameters are:

- **Duration**: length of the grains, in milliseconds
- **Pitch**: playback rate of the grains, with 1 corresponding to original pitch
- **Amp**: amplitude of the grains, 0 to 1. (the maximum value is hardcoded to 0.8 to prevent overcrowding the audio bus with 32 voices)
- **Velocity**: maximum value for the velocity of the grains (between 0.3 and 0.8)
- **Size**: size ratio of the virutal room in which the listener is placed, from 1:1 up until 10:1. bigger sizes involve particles flying around at higher speed.

### Extra functions
<p align="center">
  <img src="https://user-images.githubusercontent.com/30500998/115116663-179f5f80-9f9b-11eb-8154-c3910a00cb35.png" alt="extra_functions"/>
</p>

The two switches on the left control two more functionalities, **Doppler** and **Gravity**.
When **Doppler** is active, a doppler effect simulation is applied to all particles, making the pitch of the corresponding sound grain be affected by its movement speed.
When **Gravity** is active, a small circle appears on the visualization window on the right. By clicking on the window it is possible to define a gravitational point around which the particles will start swarming.
