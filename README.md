# Servo_Control
#include <Servo.h>

Servo myservo1;  // create servo object to control a servo
Servo myservo2;
Servo myservo3;
Servo myservo4;
Servo myservo5;
Servo myservo6;

char inChar = 0;
String inString = "";
int servo = 0;
int deg = 0;
int degree = 0;
int state = 0;
int controlServo = 0;

void control1(int degree);
void control2(int degree);
void control3(int degree);
void control4(int degree);
void control5(int degree);
void control6(int degree);

void setup() {
 
  myservo1.attach(3,1000,2000);  // attaches the servo on pin 3
  myservo2.attach(5,1000,2000);
  myservo3.attach(6,1000,2000);
  myservo4.attach(9,1000,2000);
  myservo5.attach(10,1000,2000);
  myservo6.attach(11,1000,2000);
    
  Serial.begin(9600);
  Serial.println("Hello,servo");
  Serial.println("Input your servo and degree: ");
  
  while (!Serial) {
    ;
  }
}

void loop(){
        while (Serial.available() > 0) {
              inChar = Serial.read();
            if (inChar != '\n') {             
                inString.concat(inChar);
            
            }else{
                servo = inString.substring(0,1).toInt();
                deg = inString.substring(2,5).toInt();
                inString = ""; 
            }
        }
            if(servo == 1){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control1(deg);
            }else if(servo == 2){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control2(deg);  
            }else if(servo == 3){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control3(deg);  
            }else if(servo == 4){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control4(deg);  
            }else if(servo == 5){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control5(deg);  
            }else if(servo == 6){
//              Serial.print("servo : ");
//              Serial.println(servo);
//              delay(1000);
//              Serial.print("Degree : ");
//              Serial.println(deg);
//              delay(1000);
              delay(50);
              control6(deg);  
            }
//    } 
}

void control1(int degree){
//    Serial.print("Servo 1 degree: ");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo1.writeMicroseconds(controlServo);
//    delay(50);
}
void control2(int degree){
//    Serial.print("Servo 2 degree:");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo2.writeMicroseconds(controlServo);
//    delay(50);
}
void control3(int degree){
//    Serial.print("Servo 3 degree:");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo3.writeMicroseconds(controlServo);
//    delay(50);
}
void control4(int degree){
//    Serial.print("Servo 4 degree:");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo4.writeMicroseconds(controlServo);
//    delay(50);
}
void control5(int degree){
//    Serial.print("Servo 5 degree:");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo5.writeMicroseconds(controlServo);
//    delay(50);
}
void control6(int degree){
//    Serial.print("Servo 6 degree:");
//    Serial.println(degree);
    controlServo = (degree*10.8);
    myservo6.writeMicroseconds(controlServo);
//    delay(50);
}
