//setup pins
const int pir = 7;
const int led = 13;

void setup()
{
  //setup min modes
  pinMode(pir, INPUT);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  //print status of motion detection
  int motion_detected = digitalRead(pir);
  Serial.println(motion_detected);
  
  //turn led on or off depending on motion infront of pir
  if (motion_detected == HIGH)
  {
    digitalWrite(led,HIGH);
  }else
  {
    digitalWrite(led, LOW);
  }
  delay(200);
}

//source: Anon, (2014). Arduino with PIR Motion Sensor | Random Nerd Tutorials. [online] Available at: https://randomnerdtutorials.com/arduino-with-pir-motion-sensor/.

‌