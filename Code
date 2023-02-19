// C++ code
//
#include <Servo.h>

Servo servo_bottom;
Servo servo_left;
Servo servo_right;
Servo servo_main;

unsigned int sudut;
String inString = "", temStr;
char str;
unsigned int nomor, l, i;

void setup()
{
    Serial.begin(9600);
    servo_bottom.attach(9);
    servo_left.attach(10);
    servo_right.attach(11);
    servo_main.attach(6);
    Serial.println("ROBOT ARM CONTROLLER");
}

void loop()
{
    if (Serial.available() > 0)
    {
        str = Serial.read();
        if (str != '\n')
        {
            inString += (char)str;
        }
        else if (str == '\n')
        {
            temStr = inString.substring(0, 1);
            nomor = temStr.toInt();
            temStr = inString.substring(2);
            sudut = temStr.toInt();

            Serial.print(nomor);
            Serial.print(" : ");
            Serial.println(sudut);
            switch (nomor)
            {
            case 1:
                servo_main.write(sudut);
                break;
            case 2:
                servo_left.write(sudut);
                break;
            case 3:
                servo_right.write(sudut);
                break;
            case 4:
                servo_bottom.write(sudut);
                break;
            }
            inString = "";
        }
    }
}
