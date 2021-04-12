# LED-Candle---Colby-Kosteniuk---CS-207

## Table of Contents

## Features List
Everyone knows what we all need for a good first date: fancy dinner, nice music, and of course, a beautiful candle. But what if that candle was too bright, and you're partner decides to leave. You don't want to blow a first date like that, do you? That's why I am here to present the LED Candle!

Just like a real candle, this digital light turns off when you blow on it. Unlike a real candle, this one is capable of adjusting the brightness using two buttons raning from really bright to really dim making sure you're partner doesn't go blind and that the mood is perfectly set. In this handy manual, you will learn how to build and run an LED Candle to make sure your first date doesn't become a total bust.

## Materials

Here's a list of things you'll need to make an LED Candle:
- Arduino Uno
- Breadboard
- 3 Push buttons
- 3 resistors(10k ohms each)
- LED(Any LED will do)
- Modern Device Wind Sensor Rev C4
- 5 pin header
- At least 13 jumper wires
- Sodder stick and sodder

## Instructions

### Step 1. Sodder the win sensor onto the 5 header pin
The reason this step is neccesary is because when you try to attach the wind sensor to the header, the sensor will not stick on. That's why soddering the pins to the sensor can help the sensor stick on better. And don't worry; soddering is not as scary as it sounds. All you have to do is heat up your soddering stick, take a line of sodder, and have both materialstouch the top of the pin. When the sodder line touches the sodder stick, the sodder will melt off and drop onto the pin before solidifying and therefore keeping the pin attached. This step will be easy since you only need to sodder 5 pins. However, you also need to be quick and remove the sodder stick when the melted sodder is applied, otherwise you could burn the wind sensor. When you're done, leave your soddered wind sensor to dry for an hour just for good measure

### Step 2. Build the circuit
Now that your wind sensor is ready, and it onto the breadboard along with the other materials you will be using. Using the soddered pins, attach the wind sensor to the bottom of the breadbaord with the front of the sensor pointing away from the board. You can also add the LED, but when you add it, make sure the longest leg is pointing the right way. If your LED is on the positive side of the breadbaord, then the longest leg should be facing the front. If your LED is on the negative side of the breadbaord, then the longest leg should be facing the back. Finally, add the 3 push buttons and the resistors at the bottom. The resistors should have their back leg connected to ground and the front leg connected to each button's first leg.

### Step 3. Add the wires
You will now have to give power to your breadbaord so that the project can run. This can be done by connecting parts of the circuit to an Arduino Uno via jumper wires. I used 13 for my design, but you can use as many as you see fit. Start by plugging in wires to the wind sensor. You'll notice that on the sensor there will be text above the pins. That will be where you will have to plug in jumper wires. Start by connecting GND to ground, then +V to the 5V pin, RV to the A1 pin, and TMP to the A0 pin. For the LED, I connected the longest leg to pin 13 and the shortest leg to ground. For each push buttonuse two wires; one to connect to a digital pin and the other to connect to 5V(with the exception of one button that will connect to the 3.3V pin). You can use any digital pin you like, but I have mine connected to pins 11, 9, and 2.

### Step 4. Connect your Arduino to your computer
With your circuit now complete, you can use a USB cable to connect your Arduino to your computer. You will have to download the Arduino app on your computer so you can write and upload code to your Arduino.

### Step 5. Write and upload the code
Now it's time to get this LED to work by writing some code. Fortunately, the code for this project can be found on the website for this project. It will be linked down below in the Credits section. I also added my own comments to explain what each part of the code does. However, I will take this time to talk about the new code I have added to this project near the end in the void loop():

 buttonStateb = digitalRead(buttonPinb);
 buttonStated = digitalRead(buttonPind);
if (buttonPinb == HIGH){
      if(b > 225){
        b = b;
      }
      else{
        b += 45;
        delay(100);
      }
     }

      if (buttonPind == HIGH){
      if(b < 225){
        b = b;
      }
      else{
        b -= 45;
        delay(100);
      }
     }
     
    analogWrite(led, b);
 
 As you can see, I have added a few new variables. int b is the brightness equal to 0. buttonPinb is the button that increases brightness, while buttonPind is the button that decreases brightness. Each button variable will have a buttonState to check whether each button has been pressed or not. If buttonPinb is pressed and the LED is not at full brightness, b will increase by 45. Vice versa, if buttonPind is pressed and the LED is at full capacity or lower, b will decrease by 45. This is how the LED's brightness changes since LED can produce a maximum brightness of 255. This value will be written from the analog to effect te LED. If you wrote code on Arduino for the first time, you may want to save the code to a file on your computer before you upload it.
 
 ### Step 6. Test your device
 To test your new device, blow on the wind sensor to try and turn off the LED. The wind sensor measures the wind speed and then turns that value into electrcity which can then tell the Arduino whether the LED should be off or on. When the LED is off, you can use one of the buttons to turn it back on.You can adjust the wind speed in the code to find out what works, but mine is set at 6. With all of these steps done, your LED candle is ready for that dinner date.
 
 ## Planned Features
 
 One feature that I planned on adding was to make the candle look like a real candle. I was thinking of using a small cardboard box to put my Arduino in and then cut holes in the lid for the LED, buttons, and wind sensor to stick out. Then I would put the lid on the box to make it look like a real candle. The main reason why I could not add this feature was because I got a reality check; I'd have to unplug the Arduino to make the lid fit which would turn off all the power on the device. Not to mention the lid might damage the wires. Even if it was possible to put a lid on, I would not have enough time to do it since my wind sesnor got delivered to me 2 weeks after I purchased it.
 
 ## Bugs List
 
 Despite how ingenius this idea may sound, there are still a lot of problems that I could not solve
 
 ### Whacky wind sensor
 When I uploaded my code to my project for the first time, it was working well, but barely. The LED would often turn off at random intervals sometimes when I moved my hand across the device. I decided to use the serial monitor to exploit this problem to find out that the wind speed values were inconsistently increasing and decreasing ranging from 0 mph to 100 mph. Sometimes the wind speed would even reach a nan value. The wind sensor was also still a bit lose on the header pins and I do not think I soddered them enough. If that happens to you, I would recommend that you use an object(like a book) to support the end of your wind sensor  so that it doesn't tilt when you blow on it.
 
 ### Could not get brightness to work
 So yeah, I got the first part of the project working, but my innovation for some reason did not work. Whenever I ran my additional code for the brightness function, the LED would turn on and then off when I pushed the on button. I've tried for days to solve this problem, but nothing seems to work. But hey, I still give myself credit for being able to nail the first part of the project down.
 
 If anyone has any solutions to these problems, feel free to look over my code. It can be found in my repository.
 
 ## License 
 
 license:gpl-3.0
 
 
 
 
 


