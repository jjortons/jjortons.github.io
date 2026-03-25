---
layout: post
title: "ESP32-C3 ULN2003 24BYJ-48 motor"
date: 2026-03-24 09:00:00 -0800
categories: [IdiOT]
---

# Hello!
This is a page dedicated to testing arduino, esp32, etc.. 
I am hosting this using my custom domain **miracleostrich.ca**.

<img src= "/assets/img/basic-wiring-diagram-esp32-uln2003"></img>
<img src="/assets/img/esp32-basic-wiring-01.jpg" alt="basic wiring for testing esp32-uln2003-24byj-48 motor" width="400">

arduino sketch, esp32c3 dev kit

// Define the pins connected to the ULN2003 Driver IN1-IN4
const int pin1 = 3; 
const int pin2 = 4;
const int pin3 = 5;
const int pin4 = 6;

void setup() {
  // Initialize all pins as OUTPUT
  pinMode(pin1, OUTPUT);
  pinMode(pin2, OUTPUT);
  pinMode(pin3, OUTPUT);
  pinMode(pin4, OUTPUT);
  
  Serial.begin(115200);
  Serial.println("Starting LED Chase Test...");
}

void loop() {
  // Step 1: LED A (IN1)
  digitalWrite(pin1, HIGH);
  Serial.println("LED A is ON");
  delay(500);
  digitalWrite(pin1, LOW);

  // Step 2: LED B (IN2)
  digitalWrite(pin2, HIGH);
  Serial.println("LED B is ON");
  delay(500);
  digitalWrite(pin2, LOW);

  // Step 3: LED C (IN3)
  digitalWrite(pin3, HIGH);
  Serial.println("LED C is ON");
  delay(500);
  digitalWrite(pin3, LOW);

  // Step 4: LED D (IN4)
  digitalWrite(pin4, HIGH);
  Serial.println("LED D is ON");
  delay(500);
  digitalWrite(pin4, LOW);
  
  delay(1000); // Wait a second before restarting the chase
}
