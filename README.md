ArduinoTrainController
======================

Code for an Arduino train controller project. The system is designed for one piece of hardware.

In this project, I used an Arduino Mega 2560 to control a series of relays that operated various devices on a train track.
The Arduino Mega is controled by a Netduindo, but it dosent have to be. By using a Netduino, however, I was able to offload error correction, network communications, and LCD display routines onto a much more powerful chip. The Arduino takes commands on Serial2, and they are in the form of "INT,INT,INT|". The command structure is discussed in more detail inside the arduino code.

Of interest to me in this project are two things. The most interesting thing that this code has is a linked list of C++ objects that represent the train track's turnout switches. I implemented this linked list as a way to drastically simplify managing state information as well as timing - turnouts on the train tracks must only be powered for a few seconds, otherwise they will burn out. The power blocks (sections of train track that this device can control) are placed in a much simpler struct array, as no advanced timing is needed to manage them.

Make sure, if you do try out this code, to check the serial port settings - I have a high speed set to Serial0 and Serial2.
