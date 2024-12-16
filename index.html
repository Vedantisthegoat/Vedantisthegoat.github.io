<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Motion Sensor People Counter Project</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
    }
    header {
      background-color: #333;
      color: #fff;
      padding: 10px 0;
      text-align: center;
    }
    main {
      padding: 20px;
    }
    h1, h2 {
      color: #2c3e50;
    }
    pre {
      background-color: #2c3e50;
      color: #fff;
      padding: 10px;
      border-radius: 5px;
      overflow-x: auto;
    }
    .section {
      margin-bottom: 30px;
    }
    code {
      font-family: "Courier New", Courier, monospace;
    }
    footer {
      text-align: center;
      padding: 10px;
      background-color: #333;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <h1>Motion Sensor People Counter</h1>
  </header>

  <main>
    <section class="section">
      <h2>Project Overview</h2>
      <p>This project uses a PIR motion sensor and an Arduino to count the number of people detected in a specific area. When motion is detected, the system increments a counter to track how many people are present. The count is displayed on the Serial Monitor, and an optional LED provides visual feedback when motion is detected.</p>
    </section>

    <section class="section">
      <h2>Components Needed</h2>
      <ul>
        <li>Arduino Board (e.g., Arduino Uno)</li>
        <li>PIR Motion Sensor</li>
        <li>LED (optional for visual feedback)</li>
        <li>Resistor (220Ω for LED, optional)</li>
        <li>Jumper wires</li>
        <li>Breadboard</li>
      </ul>
    </section>

    <section class="section">
      <h2>Wiring</h2>
      <p>Here's how to wire the components:</p>
      <ul>
        <li><strong>PIR Motion Sensor:</strong> 
          <ul>
            <li><code>VCC</code> -> 5V on Arduino</li>
            <li><code>GND</code> -> GND on Arduino</li>
            <li><code>OUT</code> -> Digital Pin (e.g., Pin 7 on Arduino)</li>
          </ul>
        </li>
        <li><strong>LED (optional):</strong>
          <ul>
            <li><code>Anode (long leg)</code> -> Digital Pin (e.g., Pin 13 on Arduino)</li>
            <li><code>Cathode (short leg)</code> -> GND through a 220Ω resistor</li>
          </ul>
        </li>
      </ul>
    </section>

    <section class="section">
      <h2>Arduino Code</h2>
      <p>Here is the Arduino code to count people using the motion sensor:</p>
      <pre><code>
const int motionPin = 7;  // Pin connected to the OUT of the PIR sensor
const int ledPin = 13;    // Pin connected to LED (optional for visual feedback)

int motionState = 0;      // Variable to store current motion sensor state
int lastMotionState = 0;  // Variable to store last motion state
int peopleCount = 0;      // Count the number of people detected

void setup() {
  // Initialize the serial communication
  Serial.begin(9600);
  
  // Set up the PIR sensor pin as input
  pinMode(motionPin, INPUT);
  
  // Set up the LED pin (optional)
  pinMode(ledPin, OUTPUT);
  
  // Print initial message to Serial Monitor
  Serial.println("Motion Detection System");
  Serial.println("Waiting for motion...");
}

void loop() {
  motionState = digitalRead(motionPin);  // Read the state of the PIR motion sensor
  
  // Check if motion is detected and was not previously detected
  if (motionState == HIGH && lastMotionState == LOW) {
    // Motion detected, increment people count
    peopleCount++;
    Serial.print("People Count: ");
    Serial.println(peopleCount);
    
    // Optional: Light up LED for visual feedback
    digitalWrite(ledPin, HIGH);
    delay(500);  // LED stays on for 500ms
    digitalWrite(ledPin, LOW);
  }
  
  // Check if no motion and previously motion was detected
  if (motionState == LOW && lastMotionState == HIGH) {
    // Motion ended
    Serial.println("Motion ended");
  }
  
  // Update the last motion state
  lastMotionState = motionState;
  
  delay(100);  // Small delay to prevent bouncing and to keep the loop responsive
}
      </code></pre>
    </section>

    <section class="section">
      <h2>Additional Notes</h2>
      <p>This is a basic people counter system using a single PIR sensor. If you wish to add more sensors or create a more complex people counter (tracking in and out movements), you can use multiple PIR sensors or implement additional logic to differentiate entry and exit.</p>
    </section>

    <section class="section">
      <h2>License</h2>
      <p>This project is licensed under the <strong>MIT License</strong>. Feel free to modify and use the code as you wish!</p>
    </section>
  </main>

  <footer>
    <p>Created by [Your Name]. &copy; 2024</p>
  </footer>
</body>
</html>
