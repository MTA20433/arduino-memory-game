# arduino-memory-game
A memory game built using an Arduino Uno - watch the [presentation video](https://www.youtube.com/watch?v=J5NjgtZ_BkU)!

## Storyboard
Starting out, we devised a storyboard as a means of quantifying how our solution would work on a specific scenario, along with exactly what problem it would solve. The storyboard can be seen on Figure 1.

* Our story board is titled “being able to bring a memory game away from home”.
The problem/need is that the user cannot bring their current memory game and easily play it in confined spaces. This is shown in the second frame.
* The context of interaction is when the user puts the solution in their pocket (which should be seen as a metaphor) in order to bring it with them. This is shown in the third frame.
* An illustration of the tasks enabled by the solution is seen in the third and fifth frames, where the user is able to put the solution into their pockets and use it in the confined spaces of the backseat of a car.
* The different types of feedback is shown in the fourth frame of the storyboard, where the solution is shown flashing and making sounds after a user clicks it.
* Finally, the storyboard ends in the fifth frame with the user appily using the solution in a way that the previous games did not allow for.

![storyboard figure](https://www.dropbox.com/s/llshgfezcufet3a/storyboard.jpg?dl=0&raw=1)
_Figure 1: the storyboard._

## Mapping Scheme
The design also makes use of different mapping techniques. For example, the four input buttons are positioned in close proximity to- and in direct alignment with the corresponding LED lights, following the principles of proximity and arrangement. An illustration of our mapping scheme is also seen on Figure 2.

Furthermore, since each input mechanism only controls two states (pressed/not pressed), with eight states in total, we use a linear discrete input type in the form of buttons.

In terms of feedback types, the solution has several. First off, the physical constraints and clicks of the buttons present tactile feedback to the user, guiding them to when the button has been successfully pressed. The buttons used are also of the type with very little backlash, and with elastic resistance.

Other feedback types supported by the solution include both audible- and visual feedback, with distinctly different sounds for each of the four keys, and two different multi-key tunes that play whenever a sequence is either correctly- or incorrectly repeated by the user, along with a designated LED for each of the four buttons with different colors.

![mapping scheme](https://www.dropbox.com/s/7h7cj4bgvkips80/State%20diagram.png?dl=0&raw=1)
_Figure 2: the mapping scheme._

## Circuit Diagram
As seen in Figure 3, the circuit contains the Arduino, five resistors, the four LEDs with their corresponding buttons and, finally, the speaker. 

The resistors are used to avoid power surges and breaking the LEDs or the speaker. 

The arduino pins used are the Ground port and ports D2 through D10. 

Pins D2, D4, D6 and D8 are used as output pins and they light up the leds according to the random sequence.  

Pins D3, D5, D7 and D9 are used as input pins and they read the different button presses which, through the Arduino code, are used to assess whether the sequence is correct or not.

Pin D10 is also used as an output pin and it powers up the speaker, sending the data necessary to play different sounds based on which LED is lit up.

![circuit diagram](https://www.dropbox.com/s/7wf2yuy3elj7w6f/circuit.png?dl=0&raw=1)
_Figure 3: the circuit diagram._

## State Diagram
The prototype can take on the states described in Figure 4.
It will always start from the point marked by the black dot. As seen in the demo, it will show a randomized 4-LED Sequence, after which it will transition to a receiving state. There, the user can keep inputting LEDs in a sequence, until it either matches the original random sequence (which leads to a Victory state) or it differs from it (which leads to a Lose state). The victory or lose state then plays its preset light and sound sequence, then it returns to playing a new randomized 4-LED sequence, starting a new game.

![state diagram](https://www.dropbox.com/s/oxjqsoggn5hnhen/94690374_266612734501396_2382678775843258368_n.png?dl=0&raw=1)
_Figure 4: the state diagram._

## Affordance Scheme
Due to the nature of our prototype, the affordance scheme is rather simple since the only inputs are the buttons that light up the different LEDs. The affordance scheme is visualized on Figure 5.

Each LED indicates that it is related to a light by being placed directly under that light.

The perceived affordance for each of the LEDs is that if you press a button, the LED closest to it will light up, thus adding that LED to the input sequence.

Pressing a button gives feedback in two ways: the first is the corresponding LED lighting up and the other is playing a color-specific tune.

![affordance scheme](https://www.dropbox.com/s/7iim302kp2jwe4p/affordance.jpg?dl=0&raw=1)
_Figure 5: the affordance scheme._

## Evaluation
As the mini-project was worked on in rather difficult circumstances, the final digital artifact for the mini-project is essentially a high fidelity prototype of what we had in mind when starting to work with this. Therefore, the test was conducted on the digital artifact itself, as it was very easy to build and modify using a breadboard.

Due to the same difficult circumstances, the test was only conducted on two people, as they were the only ones available to us.

The test was done using the mental model elicitation process: the participants were asked to ignore the wiring and resistors and explain what they think each element in the prototype does.

## Notes & Comparison
From the evaluation, several feedback points were gathered. 

First, the label indicating that the prototype is a memory game was very helpful in painting the right picture in the participants’ mental model.

In accordance to our affordance scheme (go back to slide 8 with the affordance scheme), both of the participants were able to tell that each of the buttons corresponds to the nearby LED and that by pressing it, the LED would turn on. (go back to last slide)

The only element that confused one of the participants was the speaker, as they were not able to tell what it was used for.

## Interaction Design Framework
Additionally, we have an illustration of the interaction design framework, devised during the design phase of the project. This illustration is shown on Figure 6.

![interaction design framework](https://www.dropbox.com/s/n9zj2btnphywl2k/94871190_899880120452404_4736658850797584384_n.png?dl=0&raw=1)
_Figure 6: interaction design framework._
