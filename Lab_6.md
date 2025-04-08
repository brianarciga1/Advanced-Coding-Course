# 🚦 Smart Crosswalk Traffic Light System (Arduino Group Lab)

## 👥 Group Size
2 students

## 🎯 Objective
Build a traffic light system with pedestrian control that:
- Cycles through green, yellow, and red for vehicles.
- Uses a **button** to activate a pedestrian crossing sequence.
- Plays a **custom melody** on a buzzer.
- Flashes **green, red, and yellow** lights for pedestrian safety.

---

## 🔌 Wiring Guide

| Component        | Arduino Pin | Notes                          |
|------------------|-------------|---------------------------------|
| Red LED          | 9           | Use 220Ω resistor to GND        |
| Yellow LED       | 10          | Use 220Ω resistor to GND        |
| Green LED        | 11          | Use 220Ω resistor to GND        |
| Pedestrian LED   | 12          | Use 220Ω resistor to GND        |
| Push Button      | 2           | Use 10kΩ pull-down resistor     |
| Buzzer           | 8           | Connect negative leg to GND     |

---

## 🧾 Starter Code

Paste this code into your Arduino IDE to get started:

```cpp
int redLED = 9;
int yellowLED = 10;
int greenLED = 11;
int pedestrianLED = 12;
int buttonPin = 2;
int buzzerPin = 8;

bool buttonPressed = false;

void setup() {
    pinMode(redLED, OUTPUT);
    pinMode(yellowLED, OUTPUT);
    pinMode(greenLED, OUTPUT);
    pinMode(pedestrianLED, OUTPUT);
    pinMode(buzzerPin, OUTPUT);
    pinMode(buttonPin, INPUT);
    
    digitalWrite(greenLED, HIGH);  // Start with green
}

void loop() {
    if (digitalRead(buttonPin) == HIGH && !buttonPressed) {
        buttonPressed = true;

        digitalWrite(greenLED, LOW);
        digitalWrite(yellowLED, LOW);
        digitalWrite(redLED, HIGH);
        digitalWrite(pedestrianLED, HIGH);

        playTune();

        for (int i = 0; i < 5; i++) {
            digitalWrite(greenLED, HIGH);
            digitalWrite(redLED, LOW);
            delay(300);
            digitalWrite(greenLED, LOW);
            digitalWrite(redLED, HIGH);
            delay(300);
        }

        for (int i = 0; i < 5; i++) {
            digitalWrite(yellowLED, HIGH);
            delay(300);
            digitalWrite(yellowLED, LOW);
            delay(300);
        }

        digitalWrite(redLED, LOW);
        digitalWrite(greenLED, HIGH);
        digitalWrite(pedestrianLED, LOW);

        delay(500);
        buttonPressed = false;
    }

    if (!buttonPressed) {
        delay(5000);
        digitalWrite(greenLED, LOW);
        digitalWrite(yellowLED, HIGH);
        delay(2000);
        digitalWrite(yellowLED, LOW);
        digitalWrite(redLED, HIGH);
        delay(5000);
        digitalWrite(redLED, LOW);
        digitalWrite(greenLED, HIGH);
    }
}

void playTune() {
    // Replace this with your own melody!
    int melody[] = { 440, 494, 523, 587, 659 };
    int noteDuration = 300;

    for (int i = 0; i < 5; i++) {
        tone(buzzerPin, melody[i]);
        delay(noteDuration);
        noTone(buzzerPin);
        delay(50);
    }
}
