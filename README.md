<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Introduction - Vedant's Website</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #f4f4f4; color: #333; margin: 20px; padding: 20px;">

    <div style="max-width: 800px; margin: auto; background-color: #fff; padding: 20px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <h1 style="color: #FF5722;">Welcome to My Website!</h1>
        <p>Hi there! My name is Vedant, and I’m 12 years old. I have a passion for technology, gaming, and sports, and I’m excited to welcome you to my very first website! It's been a fun journey building this site, and I’m super happy to finally share it with the world.</p>
        
        <p>When I’m not working on my projects or learning new things about tech, you’ll probably find me immersed in my favorite video games. Some of the games I absolutely love are <strong>Fortnite</strong> and <strong>Minecraft</strong>. They allow me to explore different worlds, be creative, and compete with friends. Video games have always been an important part of my free time, and they inspire me to keep learning and experimenting with new ideas.</p>
        
        <p>In addition to gaming, I also have a passion for playing <strong>soccer</strong>. Whether I’m playing with my friends or watching my favorite teams, soccer has always been a sport that brings me joy and helps me stay active. I enjoy the teamwork, strategy, and excitement that comes with every game. It’s a great way to balance my love for technology with staying active and engaged in the real world.</p>
        
        <p>Now, let me introduce you to the purpose of this website. This site was created as a place for me to share all the exciting <strong>projects</strong> I’m working on. Whether it's a <strong>tech project</strong>, a <strong>coding experiment</strong>, or a <strong>DIY creation</strong>, I wanted a place where I could document and showcase all my work. The best part is that I get to share these projects with the public, so I hope that my website can inspire others to create, explore, and learn as well.</p>
        
        <p>Through this website, I aim to connect with other young creators and tech enthusiasts, share knowledge, and learn new skills along the way. I’ve already started sharing some of my personal projects, but there’s so much more to come, and I’m eager to continue building and improving my skills

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>People Counting Project with Arduino</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 20px;
            color: #333;
        }
        h1 {
            color: #5C6BC0;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        pre {
            background-color: #f2f2f2;
            padding: 15px;
            border-radius: 5px;
            font-size: 16px;
            overflow-x: auto;
        }
        .image-container {
            text-align: center;
            margin-top: 20px;
        }
        .image-container img {
            max-width: 100%;
            height: auto;
        }
        footer {
            text-align: center;
            margin-top: 40px;
            font-size: 14px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>People Counting Project with Arduino and PIR Sensor</h1>
    <p>This project uses an Arduino and a PIR (Passive Infrared) motion sensor to count how many people pass by and display the count on the serial monitor. The setup also includes an LED that lights up whenever a person is detected.</p>

    <h2>Components Needed:</h2>
    <ul>
        <li>Arduino (Uno, Nano, etc.)</li>
        <li>PIR Motion Sensor</li>
        <li>LED</li>
        <li>220-ohm Resistor (for LED)</li>
        <li>Jumper Wires</li>
        <li>Breadboard (optional)</li>
    </ul>

    <h2>Wiring Diagram</h2>
    <div class="image-container">
        <img src="YOUR_IMAGE_URL_HERE" alt="Wiring Diagram">
    </div>

    <h2>Arduino Code:</h2>
    <pre>
        // Define the PIR sensor pin and LED pin
        const int pirPin = 7;   // Pin connected to the OUT pin of PIR sensor
        const int ledPin = 13;  // Pin connected to the LED

        int pirState = LOW;      // Variable to store the PIR sensor state
        int peopleCount = 0;     // Variable to store the people count

        void setup() {
          // Initialize serial communication
          Serial.begin(9600);
          
          // Set PIR pin as input
          pinMode(pirPin, INPUT);
          
          // Set LED pin as output
          pinMode(ledPin, OUTPUT);
        }

        void loop() {
          // Read the state of the PIR sensor
          pirState = digitalRead(pirPin);

          // Check if motion is detected (sensor outputs HIGH when motion is detected)
          if (pirState == HIGH) {
            peopleCount++;  // Increment the people count
            Serial.print("People count: ");
            Serial.println(peopleCount);
            
            // Turn on the LED when a person is detected
            digitalWrite(ledPin, HIGH);
            
            delay(1000);  // Delay to avoid multiple counts for the same person
            // Turn off the LED after the delay
            digitalWrite(ledPin, LOW);
          }
        }
    </pre>
</div>

<footer>
    <p>&copy; 2024 Your Name | People Counting Project</p>
</footer>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Monitoring System with Arduino and DHT11 Sensor</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 20px;
            color: #333;
        }
        h1 {
            color: #FF5722;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        pre {
            background-color: #f2f2f2;
            padding: 15px;
            border-radius: 5px;
            font-size: 16px;
            overflow-x: auto;
        }
        footer {
            text-align: center;
            margin-top: 40px;
            font-size: 14px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Temperature Monitoring System with Arduino and DHT11 Sensor</h1>
    <p>This project uses an Arduino and a DHT11 sensor to monitor temperature and humidity. The data is printed on the serial monitor, and you can use it to track the environment.</p>

    <h2>Components Needed:</h2>
    <ul>
        <li>Arduino (Uno, Nano, etc.)</li>
        <li>DHT11 Temperature and Humidity Sensor</li>
        <li>Jumper Wires</li>
        <li>Breadboard (optional)</li>
    </ul>

    <h2>Wiring:</h2>
    <p>Connect the DHT11 sensor as follows:</p>
    <ul>
        <li><strong>VCC</strong> → Connect to <strong>5V</strong> on Arduino</li>
        <li><strong>GND</strong> → Connect to <strong>GND</strong> on Arduino</li>
        <li><strong>DATA</strong> → Connect to <strong>Pin 2</strong> on Arduino</li>
    </ul>

    <h2>Arduino Code:</h2>
    <pre>
        #include <DHT.h>

        #define DHTPIN 2     // Pin where the data pin of DHT11 is connected
        #define DHTTYPE DHT11   // Define the sensor type (DHT11)

        DHT dht(DHTPIN, DHTTYPE);

        void setup() {
          // Start the serial communication
          Serial.begin(9600);
          dht.begin();
        }

        void loop() {
          // Read temperature and humidity from the sensor
          float h = dht.readHumidity();
          float t = dht.readTemperature();

          // Check if the readings failed
          if (isnan(h) || isnan(t)) {
            Serial.println("Failed to read from DHT sensor!");
            return;
          }

          // Print the temperature and humidity to the serial monitor
          Serial.print("Humidity: ");
          Serial.print(h);
          Serial.print("%  Temperature: ");
          Serial.print(t);
          Serial.println("°C");

          delay(2000);  // Delay of 2 seconds before the next reading
        }
    </pre>
</div>

<footer>
    <p>&copy; 2024 Your Name | Temperature Monitoring System</p>
</footer>

</body>
</html>
