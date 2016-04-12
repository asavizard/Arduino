/* Button Function Arduino*/
const int ledPin = 13; // the pin that the LED is attached to
int incomingByte;      // a variable to read incoming serial data into

void setup() {
  // initialize serial communication:
  Serial.begin(9600);
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // see if there's incoming serial data:
  if (Serial.available() > 0) {
    // read the oldest byte in the serial buffer:
    int tombol = Serial.parseInt();
    // if it's a capital H (ASCII 72), turn on the LED:
   for(int i =0;i<tombol;i++){
    digitalWrite(ledPin, HIGH);   // turn the LED on (HIGH is the voltage level)
    delay(500);              // wait for a second
    digitalWrite(ledPin, LOW);    // turn the LED off by making the voltage LOW
    delay(200);              // wait for a second
   }
   digitalWrite(ledPin, LOW);
   
  }
}
