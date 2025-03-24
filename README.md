# Simple-turret-Arduino-Uno
This is a training task for making an bow-like turret with Arduino Uno and 3 servo

## The main task

in 2.0-2.5 hours, make a turret that will be controlled using 2 large servos and 1 small one. The model must be original. A typical code may be the connection code for Arduino uno servos. The model should move horizontally and vertically, and a small servo is used to "release the shutter." You also need to make a projectile. The finished product should not look too collective.

## Important notes

the repository will be divided into 2 blocks - programming and the build itself. since the part related to programming and the assembly of the modules themselves is the same

## Materials and methods

Arduino Uno R3
Arduino Expansion Board

![Screenshot_70](https://github.com/user-attachments/assets/1fd7d37b-cb7f-4cde-a544-1ee86c57b055)

Servo MG995 (2 pc)

![Screenshot_71](https://github.com/user-attachments/assets/bfd0e71e-4469-40ce-aa6f-bd659536ea26)

Servo SG90 (1 pc)

![Screenshot_72](https://github.com/user-attachments/assets/4f6c2a4b-9a0f-405e-8072-275c9ae0b80d)

breadboard
Wires
The potentiometer (2 pc)
Button
Stationery elastic band

## Programming and assembly of electronic components

first, I need to connect the Arduino to the expansion board. In order to do this correctly, I found a diagram on the Internet.

![Screenshot_88](https://github.com/user-attachments/assets/64a835e9-e321-4ff4-802b-9713745c769a)

in this diagram, I see a signed pinout, because I have an expansion board in my hands, where there are no labels.

here you can see what the connection of the modules will look like.

![Screenshot_92](https://github.com/user-attachments/assets/e1116434-16b1-4f9c-9ceb-3756119cdfd3)

and here's what the result of connecting an Arduino to an expansion board should look like.

![Screenshot_93](https://github.com/user-attachments/assets/33156f63-dc0c-44a9-aa82-bbe228478d90)

ready

![Screenshot_94](https://github.com/user-attachments/assets/33fc1f9e-40e8-4913-a537-86685f084f52)

The activation code and and also the connection diagram was found by me on the [Arduino website].(https://docs.arduino.cc/learn/electronics/servo-motors/).

![Screenshot_96](https://github.com/user-attachments/assets/8358fef5-2f89-406e-b134-ff9c3d1befc3)

```#include <Servo.h>

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```
then I connected the servos and potentiometers as shown in the diagram above

![Screenshot_97](https://github.com/user-attachments/assets/7bb40149-a567-4e25-a4a1-83e247cdc4d1)

![Screenshot_98](https://github.com/user-attachments/assets/c9734537-7eee-4316-a2f7-6b49ba6b0fcb)

then I entered the code into the Arduino IDE program and started editing it, since in the example from the Arduino website, only one motor could be used.

![Screenshot_91](https://github.com/user-attachments/assets/9af27400-2346-4f01-9e24-8e93054c6054)

the code to copy with descriptions

```
#include <Servo.h> // activate the library for working with servos (it is available by default, you do not need to download it)

Servo myservo1;  // create servo object to control a servo1, there is a difference from examples code - we need to mark our servo by servo1 and servo2
Servo myservo2;

int potpin1 = 0;  // analog pin used to connect the potentiometer, we need to mark it like in example with servo
int potpin2 = 1; // use correct analogue pin number from my connection
int val1;    // variable to read the value from the analog pin, need to mark it also
int val2;

void setup() {
  myservo1.attach(9);  // attaches the servo on pin 9 to the servo object
  myservo1.attach(10); // need to use correct pin number from my connection and also mark it
}

void loop() {
  val1 = analogRead(potpin1);            // reads the value of the potentiometer (value between 0 and 1023)
  val1 = map(val1, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo1.write(val1);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there

  val2 = analogRead(potpin2);            // write command for 2 servo and also mark all
  val2 = map(val2, 0, 1023, 0, 180);     
  myservo2.write(val2);                  
  delay(15);    
}
```
result

https://github.com/user-attachments/assets/77b29c66-32ca-43d1-93ab-938e3dcac789

everything is working. now we need to connect the third SG90 servo by analogy.














## Turret v 1

In this part, I will describe my attempt to make a turret in the allotted time right during classes in FabLab.

To meet the deadline, I need to plan my work properly. While my classmates were busy connecting the motor to the board, I decided to focus on making the turret itself. It seemed to me that the modeling and manufacturing process would take too much time.

At first, I decided to search the Internet for models similar to a crossbow to see how other people implemented this idea.

[Other people models](https://www.printables.com/search/models?ctx=models&q=crossbow)

![Screenshot_75](https://github.com/user-attachments/assets/c9057c25-a1b0-4178-ac8c-f98866b3ce4b)

I chose the right one in my opinion.

[Model crossbow](https://www.printables.com/model/742153-giant-crossbow)

![Screenshot_76](https://github.com/user-attachments/assets/010ce454-8555-4d2f-9f24-dc2ed94aa9b9)

Now that I saw the example in front of my eyes, it was easier for me to model my crossbow. 

first, it was necessary to determine the size. The size range will dictate the degree of tension of the elastic band, at which its force will be enough to release the projectile.  I know from orthodontics that elastics gain the most strength if they are stretched 2-2,5-3 times. I'm not holding a special elastic in my hands, but just a stationery elastic band. Experimentally, I realized that it is better to stretch it no more than 3 times, since then it bursts. I stretched it with my hands about 2 times, applied a ruler, and it turned out to be about 100 mm.  I decided to proceed from this figure. if there is not enough tension, I will be able to adjust the tension force using a trigger, the role of which will be performed by a small SG90 servo.

### Create a model

To create the model, I used RhinoCeros 7, with which I wanted to create a .dxf format drawing for cutting on a laser engraver made of plywood, since the task time is limited and this will make the model faster than printing on a 3D printer.

to begin with, I created a square with sides of 100*100 mm, so that I would have a guideline for modeling a crossbow of the right size.

![Screenshot_77](https://github.com/user-attachments/assets/836936fb-941b-4746-8668-f4247e396cef)

then I started modeling the part where the elastic band should be stretched.

![Screenshot_78](https://github.com/user-attachments/assets/82165a4e-787f-4cde-a70d-83154c921393)

The blueprint was almost ready.

![Screenshot_79](https://github.com/user-attachments/assets/31eb1600-2889-4e61-9424-c8fe353bed2f)

The two holes on the model are modeled in order to better attach the base of the crossbow to the bowstring itself.

the drawing was uploaded in the format.DXF in order to produce 3mm plywood on a laser machine.

![Screenshot_80](https://github.com/user-attachments/assets/cc87f71d-cd49-4185-bf5c-84a9ea4ba847)

laser cut in action

https://github.com/user-attachments/assets/caa0f523-1b2d-4d07-9718-51463f306f3f

got it

![Screenshot_81](https://github.com/user-attachments/assets/5ca4dff2-bcd9-4e1b-bdfa-ee8b22f016d3)

I decided to glue the parts together using a hot glue gun.

![Screenshot_82](https://github.com/user-attachments/assets/2002f8fc-a8ce-40f7-aa1f-89b2f383b9fc)

at that moment, I folded the model and thought about how to implement vertical and horizontal movement. for some reason, the option of putting one servo on top of another did not occur to me, and I decided to implement vertical movement using the "living hinge". I have modeled a (not the most successful) option in RHinoceros. The idea was that the servo, which controls vertical movement, would be connected by an elastic band to a live loop, so I could move the turret vertically. This solution does not look efficient and reliable enough, but it is copyrighted and it could have been tried to be implemented before the deadline.

the first version was absolutely terrible

![Screenshot_83](https://github.com/user-attachments/assets/6f4269f6-e673-4f34-8dbe-bbb4f17eeafe)

the second one looked more acceptable (I positioned the hinges more tightly to increase strength) and sent it to CorelDRAW to prepare for laser cutting on 3mm plywood.

![Screenshot_84](https://github.com/user-attachments/assets/0468ce49-591e-4349-9f3e-e5662b3b701b)

I also added the same fasteners that are used to fix the elastic band tightening mechanism - I thought it would be useful for better fixation.

Laser cut in action

https://github.com/user-attachments/assets/6af1ea2f-2d88-4f15-b297-de8c139d53f5

Got it

![Screenshot_85](https://github.com/user-attachments/assets/f77a1917-f86d-4024-a038-401da200172d)

The photo shows that when trying to extract the living hinge from the laser cutter, it broke in half. After holding it in my hands, I decided that it might be worth gluing 2 pieces together to increase strength.

there will be no photos of the process of gluing parts together using a hot glue gun, as my hands are stuck to the glue, everything is stuck to the glue, even the glue is stuck to the glue. the most unpleasant sensation was getting a finger burn from hot glue, which I couldn't remove from my finger because it was too fluid. Since it was too far to the sink, I had to train my acceptance.

Result

![Screenshot_86](https://github.com/user-attachments/assets/ab4c205d-4bcf-4224-bba5-55d3d8b4a499)

https://github.com/user-attachments/assets/ae79b114-2efe-4ec7-8a89-1d0a6769c2d3

well, it was a good instructive moment, thanks to which I realized not only the disadvantages of this approach, but also that a hot-glue gun can create an elastic cushion for gluing plywood. Unfortunately, in my case it looks like a toy picked up in the trash.

https://github.com/user-attachments/assets/bc7b1274-f686-4c80-a61b-709a692c9290

Still, I had to check if it could handle the elastic band tension function.

https://github.com/user-attachments/assets/f9cd316e-602f-48a9-a642-e2a2b9dbf23f

## Create connecting parts with motors

in order to model the mounts, I need ready-made files with motors. I don't see the point in modeling them from scratch, since I can handle this task and I don't see the point in wasting time on it. other people have already done this. the meaning of my task is different

I took the model files from [this site].(https://grabcad.com/library/tag/mg995)

![Screenshot_99](https://github.com/user-attachments/assets/8f0271b0-cbe8-4294-acb1-3cc5a682507d)

[MG995 Servo].(https://grabcad.com/library/mg995-servo-3)

[mounting on the "asterisk" motor].(https://grabcad.com/library/mg995-star-horn-gear-1)

The first iteration will be with the simplest way to place the motors: one on top of the other. in fact, I will need to model the fasteners for them and make a platform so that the structure does not tip over.

First, let's start by importing the engines themselves. I imported a file format from various files in the archive into RhinoCeros 8.IGS

![Screenshot_100](https://github.com/user-attachments/assets/9eff4dd6-cec1-4c1f-85ab-653fd5e2dc2d)

I use a motor mount in the same format. after importing into Rhino, I turned the motor so that the rotating part was pointing upwards, and the mount coincided with this part.

![Screenshot_101](https://github.com/user-attachments/assets/89784c4f-a22a-496c-949e-c55aa8222dd7)

the approximate location is ready. to do this, I combined and copied the motor with the mount and positioned it so that vertical movement was possible.

![Screenshot_102](https://github.com/user-attachments/assets/b19bd237-ebad-4501-bdc2-a1ab247b41af)

at that moment, it became clear to me that vertical movement would be implemented in a slightly different way. to do this, I asked google a question and this is what it answered me.:

![Screenshot_103](https://github.com/user-attachments/assets/7c987ed6-af8e-4c98-a1af-450e4cbd3a63)

I found an [interesting article on habr].(https://habr.com/ru/articles/200516/) that explained to me how movement along different axes would occur.

![Screenshot_104](https://github.com/user-attachments/assets/883cbc34-1ea2-41e1-aad8-c2761a9dc43f)

at that moment, I thought about the fact that the cannon would have to be shifted to the side even more than I thought. but for now, I'm not going to think about how to position it vertically, as my head is already boiling.

it is also better to imagine the movement of the cannon, I was helped by such a drawing from the same google query.

![Screenshot_106](https://github.com/user-attachments/assets/6b56b44a-d93f-4af5-9d82-4c88489fb651)

now I know that such a mechanism is called a "swivel cannon".

Now it's time to add the [SG90 servo model].(https://grabcad.com/library/4145-towerpro-sg90-mini-servo-sunrobotics_in-1) here.

![Screenshot_107](https://github.com/user-attachments/assets/5664552b-2886-4c32-8d4f-8f97baf16031)

The movement system is increasingly coming together. I imported the SG90 model in the format.STEP (this, of course, was worth doing with other models). I may still be moving the models between each other, but the general scheme is already clear. Now I need to think about how I'm going to connect the motors together.

![Screenshot_108](https://github.com/user-attachments/assets/ec320de7-fc21-4163-bdf4-56e73161ac8e)

Nevertheless, I decided to position the SG90 differently, since it should act as a trigger.

![Screenshot_109](https://github.com/user-attachments/assets/25d2857b-b6dc-4efa-ba0e-ac05c9771f5b)

actually, at this stage it would be possible to look for special holders for servomotors, but I wanted to model them myself.
































