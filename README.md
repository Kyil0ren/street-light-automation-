 int ldrPin=2;
int ledPin=4;
int ledPin1=3;
int pir=3;
int a=0;
int b=0;

void setup()
{
  Serial.begin(9600);
pinMode(ledPin, OUTPUT);
pinMode(ledPin1, OUTPUT);
  pinMode(ldrPin, INPUT);
   pinMode(pir, INPUT);
  }
void loop() 
{
   a=analogRead(ldrPin);
   b=analogRead(pir);
   Serial.println(a);
   Serial.println(b);
   
if(a<85)
  {
     Serial.println("**night time**");
    if(b>500)
    {
  analogWrite(ledPin,3000);
  analogWrite(ledPin1,3000);
 delay(1800);
 Serial.println("object  present");
    }
    else
    {
      
      analogWrite(ledPin,120);
      analogWrite(ledPin1,120);
      delay(100);
      Serial.println("object  NOT present");
    }
  
   
    

  }
  else
  {
   Serial.println("00 DAYTIME  light turned off 00");
    analogWrite(ledPin,0);
      analogWrite(ledPin1,0);
    
}
}
