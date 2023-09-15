
#include "NewPing.h"


#define TRIGGER_PIN 11
#define ECHO_PIN 10

.
#define MAX_DISTANCE 400	


NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

// Motor A 
int enA = 9;
int in1 = 8;
int in2 = 7;
// Motor B 
int enB = 3;
int in3 = 5;
int in4 = 4;
int val=0;

void setup() {
  Serial.begin(9600);
  pinMode(enA, OUTPUT);
	pinMode(enB, OUTPUT);
	pinMode(in1, OUTPUT);
	pinMode(in2, OUTPUT);
	pinMode(in3, OUTPUT);
	pinMode(in4, OUTPUT);
	
   analogWrite(enA, 100);
	analogWrite(enB, 100);

	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);
  delay(1000);
}

void loop() {
delay(100);
analogWrite(enA, 200);
	analogWrite(enB, 200);
val = (sonar.ping_cm());

if (val>= 40)  {
	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);
    }
    else {
      stop();
      delay(1000);
	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, HIGH);
  delay(900);
   stop();
   delay(1000);
    }
  }
void directionControl() {
	
	analogWrite(enA, 100);
	analogWrite(enB, 100);


	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);
	
	
}

void giro() {
  analogWrite(enA, 200);
	analogWrite(enB, 200);

	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, HIGH);
  delay(900);
  
  }
void stop(){
  digitalWrite(in1, LOW);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, LOW);
  
  
  }
