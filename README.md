# Controlling-three-LEDs-using-three-buttons-via-Arduino
Controlling three LEDs using three buttons via Arduino

Project Idea:

The project controls the lighting of three LEDs using three independent buttons.
When any button is pressed, the corresponding LED is turned on.

What exactly does the project do?

1.  Contains:
• Arduino Uno board
• 3 LEDs: 1 red LED, 1 blue LED, and 1 green LED
• 3 push buttons
• 3 resistors (220 ohms) for each LED
• 3 resistors (10 kΩ) for each button
2. When connecting the circuit:
• All LEDs are off when a specific button is pressed:
• The corresponding LED begins to light up
3. The connections are made as follows:
• Each button is connected to one of the Arduino inputs (e.g., D2, D3, D4)
• Each LED is connected to one of the outputs (e.g., D8, D9, D10) via a resistor
• Each button is connected to ground and a resistor appropriately (pull-down)
4. The Arduino is programmed using code that reads the button status and turns on the LEDs based on the button pressed

Why is this project useful?

1. A great foundation for learning electronics and programming.
• Teaches students how buttons, LEDs, and digital I/O work on Arduino.
• Simplifies concepts like digitalRead() and digitalWrite().

2. Easily Scalable
• The code can be modified to control a larger number of LEDs or different functions.
• The LEDs can later be replaced with fans, motors, or audible alerts.

⸻

3. Enhances Logical Thinking Skills
• Students learn how to associate an event (the button) with a response (turning on the LED).

⸻

4. Model of Actual Control Switches
• The same idea is used in:
• Elevator panels
• Machine control panels
• Electronic keyboards

⸻

Code:

const int buttonPins[] = {2, 3, 4};

const int ledPins[]    = {8, 9, 10};



void setup() {

  for (int i = 0; i < 3; i++) {

    pinMode(buttonPins[i], INPUT_PULLUP);

    pinMode(ledPins[i], OUTPUT);

    digitalWrite(ledPins[i], LOW);

  }

}



void loop() {

  for (int i = 0; i < 3; i++) {

    if (digitalRead(buttonPins[i]) == HIGH) {

      digitalWrite(ledPins[i], HIGH);

    } else {

      digitalWrite(ledPins[i], LOW);

    }

  }

}
