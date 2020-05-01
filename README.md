int trigPin=7;
int echoPin=6;
int data=10;
long sure;
long uzaklik;

void setup()
{
  pinMode(data,OUTPUT);
  pinMode(trigPin,OUTPUT);
  pinMode(echoPin,INPUT);
  Serial.begin(9600);
  }
  void loop()
  {
    digitalWrite(trigPin,LOW);
    delayMicroseconds(5);
    digitalWrite(trigPin,HIGH);
    delayMicroseconds(10);
    digitalWrite(trigPin,LOW);
    sure=pulseIn(echoPin,HIGH);
    uzaklik=sure/29.1/2;
   
    if(uzaklik>200)
    {
    
      Serial.print("uzaklik");
      Serial.print(uzaklik);
      Serial.println("CM");
      Serial.println("musluk acildi");
     digitalWrite(data,HIGH);
     
       delay(1000);
    }
    else
    {
      
      Serial.print("uzaklik");
      Serial.print(uzaklik);
      Serial.println("CM");
      Serial.println("musluk kapandi");
      digitalWrite(data,LOW);
   
       delay(1000);
    }
    }
