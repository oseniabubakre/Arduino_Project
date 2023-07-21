int redPin = 6;
int yellowPin = 8;
int greenPin = 10;
int count;
String comment = "Please, enter the desired LED";
String response;
 


void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
pinMode(redPin, OUTPUT);
pinMode(yellowPin, OUTPUT);
pinMode(greenPin, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
Serial.println(comment);
//creating a delay
while(Serial.available()== 0){
  
}
//asking the user for response
response = Serial.readString();
if(response == "Red\n" || response == "RED\n" || response == "red\n"){
  digitalWrite(redPin, HIGH);
  digitalWrite(yellowPin, LOW);
  digitalWrite(greenPin, LOW);
}
else if(response == "Yellow\n" || response == "YELLOW\n" || response == "yellow\n"){
  digitalWrite(redPin, LOW);
  digitalWrite(yellowPin, HIGH);
  digitalWrite(greenPin, LOW);
}
else if(response == "Green\n" || response == "GREEN\n" || response == "green\n"){
  digitalWrite(redPin, LOW);
  digitalWrite(yellowPin, LOW);
  digitalWrite(greenPin, HIGH);
}
else{
  digitalWrite(redPin, LOW);
  digitalWrite(yellowPin, LOW);
  digitalWrite(greenPin, LOW);
}
}
