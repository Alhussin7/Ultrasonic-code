# Ultrasonic-code
sensor code

float distance;
unsigned long duration;
void setup()
{
pinMode(2,OUTPUT);
  pinMode(3,INPUT);
  Serial.begin(9600);
  
}

void loop()
{
  //FOR OUTPUT OPRATION
digitalWrite(2,HIGH);
  delayMicroseconds(4);
  digitalWrite(2,LOW);
  //FOR INPUT OPRATION
  duration=pulseIn(3,HIGH);
  distance=(duration/29)/2;
  
  if(distance<=60)tone(4,20550,200);
  else noTone(4);
  
  Serial.println(distance);
}
