/* Algobel Technologies & Innovations
 * Auth : Niwantha 
 * Email : niwantha@algobel.com
 * Free to Use 
 */
// Don't connect directly Ultrasonic to Nodemcu 
// Always Use logic level converter and addional power supply ( Max cuurent : 12mA : NodeMcu)
// HC-SR04+ (+) sign sensor is working with 3.3V but , sometime not working properly 
// Use pin D5 & D6 of NodeMcu 
// keep duty cycle min and delay 100sec ( Always good) 
// Use latest firmware in order to get float value correctly 
// Sensor accuracy depend on the quality of the sensor 
// Not  suitable for direct water level monitor 
// use proper enclosure box

#define TRIGGER_PIN  14 // D5
#define ECHO_PIN     12 //D6 

void setup() {
  Serial.begin (115200);
  pinMode(TRIGGER_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
 
}

void loop() {
  double duration, distance;
  
  digitalWrite(TRIGGER_PIN, LOW);  // Get Start
  delayMicroseconds(2); // stable the line 
  digitalWrite(TRIGGER_PIN, HIGH); // sending 10 us pulse
  delayMicroseconds(10); // delay 
  
  digitalWrite(TRIGGER_PIN, LOW); // after sending pulse wating to receive signals 
  
  duration = pulseIn(ECHO_PIN, HIGH); // calculating time 
  
  distance = (duration/2) / 29.1; // single path 
  
  Serial.print(distance);
  
  Serial.println(" cm");
  
  delay(100);
}
