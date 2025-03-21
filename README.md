# Simple-turret-Arduino-Uno
This is a training task for making an bow-like turret with Arduino Uno and 3 servo

## The main task

in 2.0-2.5 hours, make a turret that will be controlled using 2 large servos and 1 small one. The model must be original. A typical code may be the connection code for Arduino uno servos. The model should move horizontally and vertically, and a small servo is used to "release the shutter." You also need to make a projectile. The finished product should not look too collective.

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




















