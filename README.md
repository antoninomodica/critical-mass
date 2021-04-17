# critical-mass

## About
CriticalMass is a surround granular synthesizer based on the Boids flocking algorithm originally developed by Craig Reynolds. The audio engine is implemented in the visual programming language Max/MSP, while swarming functionalities are based on JavaScript. The aim of the project is the tight integration between the characteristics of the particle swarm and the parameters of the granular synth, creating a responsive musical instrument.

## Dependencies
- full installation of Max 8. Download from https://cycling74.com/downloads
- external objects library **spat** by IRCAM. Download https://forum.ircam.fr/projects/detail/spat/

## Usage
In the top section of the main view it is possible to pick a folder containing the samples to be used in the synth. When a file is selected via the dropdown menu, its waveform is visualized right underneath it. By highlighting a slice of the waveform it is possible to choose which section of the file is going to be used for the sound generation.

![file_selection](https://user-images.githubusercontent.com/30500998/115115647-dc4e6200-9f95-11eb-8548-088af402eef6.png)  <br/>
*File selection*


Once the desired file is selected, both the **sound** and the **flocking** engines can be started via the dedicated switches. As soon as the flocking switch is turned on, the window on the right is automatically populated with 32 particles flying around.

![control_switches](https://user-images.githubusercontent.com/30500998/115115704-16b7ff00-9f96-11eb-96d3-ffaf5294e12a.png) <br/>
*Control window*


The control area contains the main parameters of the synthesizer
