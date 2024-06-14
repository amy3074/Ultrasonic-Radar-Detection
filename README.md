# Ultrasonic-Radar-Detection
The Arduino ultrasonic detector measures distance by timing sound wave echoes, calculating half the sound's travel time multiplied by air's sound speed for object proximity.
#define trigPin 9
#define echoPin 10

// Speed of sound in cm/us
const float speedOfSound = 0.0343;

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  unsigned long duration;
  float distance;
  
  digitalWrite(trigPin, LOW); 
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  // Measure the pulse duration returned by the sensor
  duration = pulseIn(echoPin, HIGH);
  
  // Calculate the distance based on the speed of sound
  distance = (duration / 2.0) * speedOfSound;
  
  // Check if the distance is within the sensor's range
  if (distance >= 1000 || distance <= 2){
    Serial.println("Distance = Out of range");
  }
  else {
    Serial.print("Distance = ");
    Serial.print(distance);
    Serial.println(" cm");
  }
  
  // Wait a bit before the next measurement
  delay(500);
}
