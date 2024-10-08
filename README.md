# Robotic_Arm
Abstract:
      This report details a prosthetic arm system using Arduino Uno microcontrollers, 3D printed parts, servo motors, flex sensors, and protective resistors. The system detects muscle movements via flex sensors in a glove, processes them through the Arduino, and controls servo motors to enable precise arm movements. A power bank provides energy, ensuring portability. The prosthetic arm is designed for affordability, customization, and durability, aiding individuals with upper limb amputations in daily tasks. Despite its benefits, challenges like complexity and limited sensory feedback remain, indicating a need for further research to improve functionality and user experience.
      
   Arduino code:
//Flex Sensor controlled Robo Hand
 
//Idle  790--835--793--859--827--
//Close 880--844--802--866--831--
 
#include <Servo.h>
 
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;
 
int flex1 = A1;
int flex2 = A2;
int flex3 = A3;
int flex4 = A4;
int flex5 = A5;
;
void setup()  
{
 Serial.begin(9600);
 servo1.attach(2);
 servo2.attach(3);
 servo3.attach(4);
 servo4.attach(5);
 servo5.attach(6);
}
 
void loop()
{
 int flex1_pos;  
 int servo1_pos;  
 flex1_pos = analogRead(flex1);
 servo1_pos = map(flex1_pos, 840, 900, 180, 0);
 servo1_pos = constrain(servo1_pos, 180, 0);  
 servo1.write(servo1_pos);
 
 int flex2_pos;  
 int servo2_pos;  
 flex2_pos = analogRead(flex2);
 servo2_pos = map(flex2_pos, 879, 882, 0, 180);
 servo2_pos = constrain(servo2_pos, 0, 180);  
 servo2.write(servo2_pos);
 
 
 int flex3_pos;  
 int servo3_pos;  
 flex3_pos = analogRead(flex3);
 servo3_pos = map(flex3_pos, 828, 824, 180, 0);
 
 
 servo3_pos = constrain(servo3_pos, 180, 0);  
 servo3.write(servo3_pos);
 
 int flex4_pos;  
 int servo4_pos;  
 flex4_pos = analogRead(flex4);
 servo4_pos = map(flex4_pos, 874, 878, 0, 180);
 servo4_pos = constrain(servo4_pos, 0, 180);  
 servo4.write(servo4_pos);
 
 int flex5_pos;  
 int servo5_pos;  
 flex5_pos = analogRead(flex5);
 servo5_pos = map(flex5_pos, 855, 851, 180, 0);
 servo5_pos = constrain(servo5_pos, 180, 0);  
 servo5.write(servo5_pos);
 
 
 /*
Serial.print(servo1_pos);
Serial.print("--");
Serial.print(servo2_pos);
Serial.print("--");
Serial.print(servo3_pos);
Serial.print("--");
Serial.print(servo4_pos);
Serial.print("--");
Serial.print(servo5_pos);
Serial.println("--");
*/
 
Serial.print(flex1_pos);
Serial.print("--");
Serial.print(flex2_pos);
Serial.print("--");
Serial.print(flex3_pos);
Serial.print("--");
Serial.print(flex4_pos);
Serial.print("--");
Serial.print(flex5_pos);
Serial.println("--");
 
 delay(300);
 

}

Conclusion:
    The prosthetic arm system, which combines Arduino Uno, 3D printed parts, servo motors, flex sensors, and a power bank, represents a major leap in assistive technology. It offers benefits like customization, affordability, ease of use, and versatility, helping individuals with upper limb amputations regain mobility and independence. However, challenges such as assembly complexity, limited sensory feedback, and battery dependence need to be addressed. The system's applications are broad, including daily living, work, recreation, and medical training. Future advancements and user feedback will be crucial in improving its accessibility and functionality, underscoring the system's potential to enhance quality of life for users.

