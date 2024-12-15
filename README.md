this is a collection of my Arduino programs the first one is a potentiometer controlling the brightness of a LED wothout using the the map function: const int hitPin = A0;
const int ledPin = 9;

void setup() { pinMode(ledPin, OUTPUT); }

void loop() { int hitValue = analogRead(hitPin);

int brightness = hitValue * 255 / 1023;

analogWrite(ledPin, brightness);

delay(10); }

This code is with using the mapfunction: const int hitPin = A0;
const int ledPin = 9;
void setup() {

pinMode(ledPin, OUTPUT); }

void loop() {

int hitValue = analogRead(hitPin);

int brightness = map(hitValue, 0, 1023, 0, 255);

analogWrite(ledPin, brightness);

delay(10); }
