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


![image](https://github.com/user-attachments/assets/23bcf864-8648-4648-b998-17bed0c76109)


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

bool buttonPressed = false;   // Track if the button has been pressed

void setup() {
    pinMode(redLED, OUTPUT);     
    pinMode(yellowLED, OUTPUT);  
    pinMode(greenLED, OUTPUT);   
    pinMode(pedestrianLED, OUTPUT);  
    pinMode(buzzerPin, OUTPUT);
    
    pinMode(buttonPin, INPUT);
    digitalWrite(greenLED, HIGH);  // Start with the green light
}

void loop() {
    if (digitalRead(buttonPin) == HIGH && !buttonPressed) {  
        buttonPressed = true;  // Register button press to avoid multiple triggers

        // Turn off green light, turn on red and pedestrian light
        digitalWrite(greenLED, LOW);        
        digitalWrite(yellowLED, LOW);       
        digitalWrite(redLED, HIGH);         
        digitalWrite(pedestrianLED, HIGH);  

        // Play a short tune on the buzzer
        playTune();

        // Pedestrian crossing delay
        delay(3000);  

        // Flash yellow before switching back
        for (int i = 0; i < 5; i++) {
            digitalWrite(yellowLED, HIGH);
            delay(500);
            digitalWrite(yellowLED, LOW);
            delay(500);
        }

        // Reset lights: back to green
        digitalWrite(redLED, LOW);
        digitalWrite(greenLED, HIGH);
        digitalWrite(pedestrianLED, LOW);

        delay(500);  // Small delay before allowing another button press
        buttonPressed = false;  // Reset button state
    }

    // Normal traffic cycle (if no button is pressed)
    if (!buttonPressed) {
        delay(5000);  // Green light stays on

        // Green → Yellow
        digitalWrite(greenLED, LOW);
        digitalWrite(yellowLED, HIGH);
        delay(2000);

        // Yellow → Red
        digitalWrite(yellowLED, LOW);
        digitalWrite(redLED, HIGH);
        delay(5000);

        // Red → Green
        digitalWrite(redLED, LOW);
        digitalWrite(greenLED, HIGH);
    }
}

// Function to play a short tune on the buzzer
void playTune() {
    int melody[] = {1000, 1200, 1400, 1200, 1000}; // Simple beep sequence
    int noteDuration = 300;  // Duration of each note in milliseconds

    for (int i = 0; i < 5; i++) {
        tone(buzzerPin, melody[i]);
        delay(noteDuration);
        noTone(buzzerPin);
        delay(50);  // Small pause between notes
    }
}
```

---

## 🎵 Melody Challenge

🎶 Replace the values in `melody[]` with your own pattern of frequencies (Hz) or musical notes like `NOTE_C4`, `NOTE_D4`, etc.

> Use this tone reference:  
> [Arduino Tone Reference – Notes and Frequencies](https://www.arduino.cc/en/Tutorial/BuiltInExamples/toneMelody)

---

## ✅ Lab Checklist

- [ ] Wire your circuit correctly.
- [ ] Upload and run the code.
- [ ] Replace the melody with your custom tune.
- [ ] Ensure red, green, and yellow LEDs flash during pedestrian crossing.
- [ ] Troubleshoot with your partner.

---

## 🧠 Reflection Questions

1. What are the advantages and disadvantages of using a push-button system versus using sensors or automated timers for pedestrian crossings?
2. What improvements would you make to this current system?

---
