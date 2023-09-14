Control software
====

This directory must contain code for control software which is used by the vehicle to participate in the competition and which was developed by the participants.

All artifacts required to resolve dependencies and build the project must be included in this directory as well.
// Motor A 
int enA = 9;
int in1 = 8;
int in2 = 7;
// Motor B 
int enB = 3;
int in3 = 5;
int in4 = 4;

void setup() {

	pinMode(enA, OUTPUT);
	pinMode(enB, OUTPUT);
	pinMode(in1, OUTPUT);
	pinMode(in2, OUTPUT);
	pinMode(in3, OUTPUT);
	pinMode(in4, OUTPUT);
	
	
	digitalWrite(in1, LOW);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, LOW);
}
void loop() {
	directionControl();
	delay(900);

}
void directionControl() {
	
	analogWrite(enA, 100);
	analogWrite(enB, 100);


	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);
	delay(2000);
	
  analogWrite(enA, 200);
	analogWrite(enB, 200);

	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, HIGH);
}
