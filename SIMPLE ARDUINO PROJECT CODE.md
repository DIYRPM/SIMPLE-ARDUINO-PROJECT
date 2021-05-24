#define led 13

#define trig_Pin 9
#define echo_Pin A0

int duration, distance; 
void setup() {
  // put your setup code here, to run once:
pinMode(led, OUTPUT);
pinMode(trig_Pin, OUTPUT);
pinMode(echo_Pin, INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(trig_Pin, LOW);
delayMicroseconds(2);
digitalWrite(trig_Pin, HIGH);
delayMicroseconds(10);
digitalWrite(trig_Pin, LOW);
duration = pulseIn(echo_Pin, HIGH);
distance = duration * 0.032 / 2;
if (distance < 5){
  digitalWrite(led, HIGH);
  }
else{
  digitalWrite(led, LOW);
  }
}
