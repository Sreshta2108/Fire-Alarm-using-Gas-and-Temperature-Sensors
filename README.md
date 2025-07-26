🔥 Fire Alarm System using Gas and Temperature Sensors

This project implements a simple but effective fire detection and alarm system using MQ-2 Gas Sensor and LM35 Temperature Sensor, integrated with an Arduino UNO. When dangerous levels of gas or temperature are detected, the system triggers an alarm (buzzer or LED) to alert nearby users.


---

📌 Features

🔍 Real-time monitoring of gas leaks (smoke, propane, methane).

🌡 Continuous measurement of ambient temperature.

🚨 Triggers alarm when either sensor crosses a critical threshold.

🖥 Displays live sensor values on Serial Monitor or LCD (optional).

⚙ Simple and low-cost fire safety prototype.



---

🧰 Components Used

Component	Quantity

Arduino UNO	1
MQ-2 Gas Sensor	1
LM35 Temperature Sensor	1
Buzzer	1
Red LED (optional)	1
16x2 LCD Display (optional)	1
Breadboard & Jumper Wires	-
Resistors (220Ω, 10kΩ)	-



---

⚡ How It Works

1. MQ-2 Sensor measures gas concentration in the air.


2. LM35 Sensor outputs temperature as analog voltage.


3. Arduino reads both values and compares with pre-defined thresholds:

Gas level > 300 (example)

Temperature > 50°C (example)



4. If either is true:

Buzzer rings or LED blinks.

Message is shown on Serial Monitor or LCD (optional).





---

🖥 Sample Arduino Code Snippet

#define gasPin A0
#define tempPin A1
#define buzzer 8

void setup() {
  pinMode(buzzer, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int gasLevel = analogRead(gasPin);
  int tempADC = analogRead(tempPin);
  float temperature = (tempADC * 5.0 * 100.0) / 1024;

  Serial.print("Gas: "); Serial.print(gasLevel);
  Serial.print(" | Temp: "); Serial.println(temperature);

  if (gasLevel > 300 || temperature > 50) {
    digitalWrite(buzzer, HIGH);
  } else {
    digitalWrite(buzzer, LOW);
  }

  delay(1000);
}


---

🛠 Setup Instructions

1. Connect MQ-2 to analog pin A0, LM35 to A1.


2. Connect buzzer to pin 8 (with resistor).


3. Upload code to Arduino via Arduino IDE.


4. Open Serial Monitor at 9600 baud to view readings.


5. Test with a lighter (no flame) for gas or warm object for temp.




---

📷 Optional Add-ons

Integrate 16x2 LCD for real-time display.

Send SMS/email alerts using GSM or ESP8266.

Build a custom PCB for deployment.



---

📂 Folder Structure

fire-alarm-gas-temp/
├── fire_alarm.ino         # Arduino sketch
├── circuit_diagram.png    # Circuit diagram (Fritzing/Tinkercad)
├── README.md              # Project description
├── images/                # Project photos/screenshots


---

🧠 Learnings

Sensor interfacing with Arduino.

Real-world safety applications using IoT basics.

Simple analog-to-digital conversion.

Conditional logic in embedded systems.




Tinkercad Model:
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6ce44570-a177-488a-ab18-ef8d82f41500" />

