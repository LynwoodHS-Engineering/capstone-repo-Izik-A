The code used for both the button and pneumatic system were both made in In Arduino's coding language, C++. The following codes are listed below and will be added upon as more developments in the project occur.

# Pneumatic System

const int buttonPin = A0;      // Pin connected to NO
int buttonState = HIGH;        // Current reading of the button
int lastButtonState = HIGH;    // Previous reading of the button

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Use internal pull-up resistor
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  // Detect press: LOW now, HIGH before
  if (lastButtonState == HIGH && buttonState == LOW) {
    Serial.println("Button Pressed"); // Trigger once
  }

  lastButtonState = buttonState; // Save state for next loop
}
