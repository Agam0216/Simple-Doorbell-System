#  Simple Push-Button Doorbell System (Arduino Uno)

A basic doorbell circuit built with an Arduino Uno, a push button, and a piezo buzzer.  
Pressing the button rings the buzzer instantly; releasing it stops the sound with no delay.

---

# Project Links


|  Full Documentation (Google Docs) | [Click here to view](https://docs.google.com/document/d/1ypRlxx5up5wjHlWGxvLygGgnbgzay2gE5QpVM28c-aA/edit?usp=sharing) |
| Simulation (Wokwi) | [Open the simulation](https://wokwi.com/projects/479104164140573697) |



##  About

The Google Doc above contains the complete write-up:
- Components list and wiring table
- Step-by-step build instructions
- Explanation of why no external resistor was needed
- Output screenshots from the simulation
- Full Arduino source code

---


---

##  Code

```cpp
const int BUTTON_PIN = 2;
const int BUZZER_PIN = 8;

void setup() {
  pinMode(BUTTON_PIN, INPUT_PULLUP);
  pinMode(BUZZER_PIN, OUTPUT);
}

void loop() {
  if (digitalRead(BUTTON_PIN) == LOW) {
    tone(BUZZER_PIN, 1000); // Ring buzzer
  } else {
    noTone(BUZZER_PIN);     // Stop buzzer
  }
  delay(10);
}
