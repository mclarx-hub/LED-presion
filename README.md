# LED-presion
Led con sensor de presion

int pinBoton = A2;
int valorBoton;
int ledPin= 3;
int valMap;


void setup() {
  // put your setup code here, to run once:
pinMode(pinBoton, INPUT);
pinMode(ledPin, OUTPUT);
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
valorBoton= analogRead(pinBoton);
valMap= map(valorBoton, 0, 1023, 0, 255); 
valMap=constrain(valMap, 0, 255);
analogWrite(ledPin, valMap);
Serial.println(valMap);
//Serial.println(valorBoton);
//delay(250);

}
