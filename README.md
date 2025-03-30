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

### Create connecting parts with motors

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

in real life, I started modeling the "advanced" version 2 at this stage, and returned to this one later.

## Turret v2

### Create a model

The first part of creating models is described in version 1.

There have been many corrections and alterations. So I will focus only on the main points.

this is the final result after several corrections.

![Screenshot_126](https://github.com/user-attachments/assets/75c7ad07-f00d-44c9-a4c3-fbd35eef6203)

I've taken a few points as a basis.: 

1) Since, due to the location of the engines I have chosen, the turret will have a clear shift in the center of gravity towards the cannon itself, I decided to create a large base that should give stability to the structure;
2) also, for balance, I positioned the volumetric part in the opposite direction from the gun. initially, I wanted to make a support wheel there, which would provide another fulcrum, but I decided that I would have to make changes to the design, which would take too much time anyway, and abandoned this idea.;
3) the motors will be fixed by matching the shape of the holders to the shape of the motors;
4) The upper part of each of the motors will remain free. instead of screws, I will try to use specially modeled pins on the holders.;
5) the big problem (which made me redo the holders) was that I underestimated the size of the wire. There should be plenty of room in the final version;
6) I wanted to avoid angular shapes as much as possible in order to train myself to a different visual mindset during modeling, as well as to make the turret more stylish.;
7) I use PLAY filament for printing, as it prints quickly and has a fairly low shrinkage;
8) during the simulation, I did NOT provide for shrinkage compensation, nor did I adjust the geometry to make the landing of the motor more free. keep this in mind if you try to repeat the project.;
9) I turned out to have too many components and to fix them with each other, I probably have to use an acrylate glue. I should have made the structure more monolithic;
10) the weaknesses that are obvious to me at the moment, while the final sample is being printed, are the fixation of holders with nozzles on the motors and excessive load on the vertical servo;

### Important notes

now I will focus on a few points in more detail, since I am not sure that I have the strength to describe the modeling step by step.

this is what the model version looked like when I was still planning to make a wheel as an additional support for a vertical servo. there were flaws, for example, one layer at a time on the cutouts of the crossbow, an unfinished arrow, but at this stage I launched the printing platform, as well as horizontal and vertical holders for the servo. At that moment, the idea of "hiding the wires inside the structure" seemed attractive to me, but I did not approach it carefully enough.

![Screenshot_110](https://github.com/user-attachments/assets/48ebe76c-ac53-420f-858b-aa52fa60cd89)

The printer is FlashForge V5 Pro, the filament is Pla Geeetech, printing is carried out from a Reality Space Plus filament dryer, the filament was dried at 50 degrees, heating was about 1-1.5 hours before printing. Slicing in the OrcaSLicer 2.2 0.4  nozzle.

slicing

![Screenshot_116](https://github.com/user-attachments/assets/ab5a5bf1-e51e-4101-90f5-db783f0f6823)


I had to redo the holder for the SG90 servo, as its rounded shape did not allow it to be adequately positioned on the printing table.

![Screenshot_112](https://github.com/user-attachments/assets/41263715-8a48-408f-a516-308f40725453)

I either had to change the model from scratch or add a plane to it so that it could be adequately printed.

detail before adding the plane

![Screenshot_114](https://github.com/user-attachments/assets/5ba6c60d-9258-498b-9999-fb8df56a0830)

a detail with an added plane, but not yet edited

![Screenshot_115](https://github.com/user-attachments/assets/996a166f-1141-4d34-be04-eb0f8c03368d)

![Screenshot_117](https://github.com/user-attachments/assets/8b98a247-f346-4a55-a8b0-a2fe37106156)

despite the modification of the model, I had to use the support. this is my first experience of manually setting supports. I have drawn the areas where, in my opinion, it is necessary to put tree supports.

![Screenshot_119](https://github.com/user-attachments/assets/a324558a-7ed8-4ad4-b006-d5909ba78c86)

I also had to print the parts vertically to balance the center of gravity (because of their convex shape). I didn't want to change the form, so I also used the support

![Screenshot_120](https://github.com/user-attachments/assets/48b3b4b9-3213-43f6-8559-780e0470d84a)

the result of the first print

![Screenshot_127](https://github.com/user-attachments/assets/bee1a559-470d-4140-a7f0-2a3a3f1250dc)

the horizontal motor holder fits perfectly into the platform. but there were problems with attaching the motor to the nozzle, which is why I had to redo the part. the problem arose because I got confused in the large number of objects on the screen and missed what I had done with the "Boolean difference"

https://github.com/user-attachments/assets/25f7b200-42bd-44e9-91b0-6c6e4b00b803

The fit of the lower part of the motor seemed normal and tight enough to me, but I couldn't check it because I made a mistake with the size of the channel for the wires.

https://github.com/user-attachments/assets/65a23e0b-7391-4b7f-87bc-26e12df502be

the problem with the channel for the wires was that it was not large enough

https://github.com/user-attachments/assets/c884aaf5-ebb3-4648-a74f-3de0955774e6

I tried to solve this problem by using dental micro-examination.

![5411559949038908745](https://github.com/user-attachments/assets/464c4bfc-d638-444f-ad3b-55859c9d93e6)

unfortunately, there were chips, which turned out to be quite difficult to remove. Perhaps the problem is partly related to the low melting point of PLA, and during processing at 30,000 rpm, it was locally heated and the chips were slightly fused. I was trying to use wire cutters and a wrench for the nuts from my 3d printer

![5411559949038908746](https://github.com/user-attachments/assets/f6faee17-adc7-49bd-82b1-02a20860c1ee)

![5411559949038908747](https://github.com/user-attachments/assets/e331b57d-e70f-4cc3-9519-27b00e8613d4)

finally, I decided to leave the platform, as it remained functional after the correction. The correction of the holders did not work out, so I decided to fix the errors on the 3d model itself and re-print it.

![5411559949038908748](https://github.com/user-attachments/assets/5b86bc23-b033-47a9-a96d-5f817f422102)

during the correction of 3D models, the "channels" for the wires became too large and the overhang area increased. I had to make the roof of the channel rounded to improve the print quality.

an example of a corrected channel

![Screenshot_128](https://github.com/user-attachments/assets/b4528b9b-edbe-4be3-ae77-b51ef8dcb4ea)

I uploaded the corrected models along with the models that I haven't printed yet to OrcaSlicer.

![Screenshot_125](https://github.com/user-attachments/assets/a2b5660f-c116-4709-9f0e-298406563991)

The printing process

https://github.com/user-attachments/assets/13c5059e-5b36-4f48-8a3b-ab2aa565bd26

Ready

![Снимок экрана (17)](https://github.com/user-attachments/assets/b2379ac4-dd7e-4053-8e19-1420ab17a4f3)

But there was some problems. again, I did not provide enough space for the wires, because I did not appreciate that I needed to provide ways to insert the motor into the holder. To fix this, I had to use a dental machine again to drill the models.

![Screenshot_237](https://github.com/user-attachments/assets/5c9e318c-7909-4f89-93b8-636fa9b86781)

after the modification, the fixation of the motors in the holders became excellent. I also had to remove the internal bushings, since the motors are held by fixing the walls of the motors with a holder.

![Screenshot_238](https://github.com/user-attachments/assets/2cb50689-93ba-4f8d-8377-c6384e4278be)

![Screenshot_239](https://github.com/user-attachments/assets/a193a429-c654-4c8e-ad08-50ad5a5110f1)

let's check the fixation of the horizontal motor holder in the platform

https://github.com/user-attachments/assets/2ac87a01-2f8f-43cb-a191-a22ad174774b

the weak part of the project also becomes obvious - the idea of installing a holder in the nozzles for motors clearly failed.

https://github.com/user-attachments/assets/52dfdcd5-58bd-42e1-8c4a-2cefd9eaca6b

There is also a good fixation of the sg90 servo into its holder.

![Screenshot_240](https://github.com/user-attachments/assets/8a3b36d9-b999-402f-b833-7b09b3aa01b0)

there was a problem with one of the parts for assembling the bow - I did not provide the tolerances and the beam got stuck inside the hemisphere. I didn't like the option of sawing it, since the walls are quite thin and I can permanently damage the model.

![Screenshot_241](https://github.com/user-attachments/assets/20956203-14a2-47d8-809d-01030c383d5d)

to install the beam in the hemisphere, it had to be literally hammered there.

https://github.com/user-attachments/assets/a4b011a6-cd29-4493-bc1e-ecf17208657e

Fortunately, everything worked out.

![Screenshot_242](https://github.com/user-attachments/assets/f5d4edb7-ddc7-425e-9859-565c75269659)

I also did not provide for a good fixation of the adapter from the sg90 servo to the bow. this happened because I got confused about Boolean operations and didn't cut out everything. I also did not provide for the distance at which the nozzle on the sg90 is located from the servo housing itself.

![Screenshot_243](https://github.com/user-attachments/assets/60f27f8e-50f7-4972-9384-cc9b2efef8a2)

since this problem became apparent already at school and there is no dental motor in FabLab, I tried using a screwdriver.

![Screenshot_244](https://github.com/user-attachments/assets/9ea01f2c-1892-497b-996b-60dc239940de)

In order not to damage my hands during this process, I tried to fix the model using a special FabLab holder and pliers. I do not recommend repeating this experience because of the poor fixation of the model during drilling.

![Screenshot_245](https://github.com/user-attachments/assets/8d79f099-db70-452f-b58b-5bbd032159fb)

despite my efforts, the result was unsatisfactory. I didn't want to re-model the model and print it, but I guess I'll have to do this.

![Screenshot_246](https://github.com/user-attachments/assets/a983f141-6036-4a36-a6d9-20c3271443bc)

in order to remove the supports from the parts that are supposed to balance the structure, I used special pliers from a 3D printer.

![Screenshot_247](https://github.com/user-attachments/assets/f65c65e2-feea-4397-bb40-48a0fc05c8ea)

the result was acceptable . my first experience with installing the supports manually on an FDM printer turned out to be successful

![Screenshot_248](https://github.com/user-attachments/assets/3642354b-7555-445d-88b5-1bf43eccdd06)

I re-modeled the adapter from the sg90 servo to the bow in Rhino, also made a new arrow model so that it was wider and better fixed on the bow plane, and also added 2 models of small supports for better fixation of the bow in the adapter to the sg90

![Screenshot_249](https://github.com/user-attachments/assets/43784b96-8bfe-4f76-86de-92bbbcaba83b)

![Screenshot_250](https://github.com/user-attachments/assets/561d3b97-f6db-4b89-b166-515801331e51)

slicing was done in OrcaSLicer by a teacher from FabLab

![Screenshot_251](https://github.com/user-attachments/assets/84c91b3a-445e-4724-804d-99976d469197)

material - PLA from SolidFilament

![Screenshot_252](https://github.com/user-attachments/assets/fbe6ce07-f306-43a6-9aef-461c5b9a8f91)

3d printing on the FlashForge a5m printer

https://github.com/user-attachments/assets/f44737e5-a3da-4e1b-8f72-55dd6a3c34df

Ready

![Screenshot_253](https://github.com/user-attachments/assets/544c102a-e180-4cd4-87e0-342dce508006)

The adapter for sg90 servos was a great fit. I was worried about fixing it with the motor, but it holds without additional accessories.

![Screenshot_254](https://github.com/user-attachments/assets/e1d33acd-eb81-43b9-97e1-a589ff912e2e)

view of the assembled model. adapters for additional mounting are also visible here. I attached them with a hot glue gun. traces of glue are also visible in the photo. Unfortunately, they didn't work out the way they look in the simulation. It was probably worth making them bigger.

![Screenshot_255](https://github.com/user-attachments/assets/1fe648ad-8fa1-4160-b292-00628954b655)

It is worth adding that the nozzles for the servo were also glued with a hot-glue gun to the holders themselves.

![Screenshot_256](https://github.com/user-attachments/assets/5b407743-e9d6-4ece-8ef3-b6d3dcfde20b)

view of the landing pad with applied glue

![Screenshot_257](https://github.com/user-attachments/assets/f1360b3a-79ca-4394-b5f8-94a4868934d0)

ready-made view of the assembled cannon

![Screenshot_258](https://github.com/user-attachments/assets/aac44647-a60e-4797-9358-280abee852d1)

at this stage, I double-checked the wiring connection again. in fact, it was at this stage that I changed the program code so that the sg90 servo would work (a reference to the programming point)

![Screenshot_259](https://github.com/user-attachments/assets/c65804a6-6b77-44b7-a922-52376182437c)

Let's check the mobility of the cannon

https://github.com/user-attachments/assets/06f000eb-c887-46e0-982a-5e6f9a20a641

an important point: I did not use the arrow that I originally printed for two reasons: I made it too narrow for the bow platform and it also turned out to be too light. so I used an arrow that I modeled based on the size of the landing pad. here we found out another nuance: the landing pad turned out to be too short in length, which is why the boom was outweighed by the leading edge. to fix this, I glued the failed parts to the tail of the boom to change the center of gravity. It's not much, but it has improved the situation a bit.

view of the cannon with the final version of the arrow with a weighting

![Screenshot_260](https://github.com/user-attachments/assets/f3f318ed-651b-4116-a4b0-2d0d5246ec56)

I also had to connect the wires to each other to increase the distance to the microcontroller somewhat.

the task has already been completed. But let's check how the cannon fires.

https://github.com/user-attachments/assets/c0ba1162-a51b-4361-8790-3373cb76dddb

Of course, I wouldn't call it a powerful weapon, but the cannon works.

### What's next?

if I have time, I want to change the model. here are a few points that I want to fix: hide the wires inside the cannon body; change the fixation of the parts with each other so that glue is not required; change the shape of the bow and arrow to improve balance and range; make a housing for the microcontroller so that a beautiful and functional control panel comes out; change the design so as to reduce the number of elements, which the model consists of. These points will help me to work on mistakes, train my engineering thinking and take into account the difficult moments of modeling and assembly in the future.

















































































