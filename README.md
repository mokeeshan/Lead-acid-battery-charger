# Lead-acid-battery-charger
Semester 4 Electronics 3 Project

Project Members:-

                  Gajaanan S. -190185D
                  
                  Pankajan T. -190428D
                  
                  Luxshan S. -190364C
                  
                  Mokeeshan V.-190395V

## Overview of the project
* Lead Acid Batteries was the first-ever rechargeable battery type that was introduced in 1859. It has acid 
and leads composites. The lead is also added with selenium, tin, calcium, and antimony to improve the 
strength of lead. With the help of the switching circuit in this project, we planned to use both a constant 
current and a constant voltage source to charge the 24V lead-acid battery with a current of 8A.

### Constant voltage charging

* The lead-acid battery charging voltage is kept constant throughout the charging period. For our purpose 
24V lead-acid battery, nearly 28-30V source is wanted. Also, we will use this charging voltage in the 
form of a PWM signal to effectively charge our battery design. At the starting of battery charging time, 
a large current is absorbed by the battery. After sometimes absorbing current will be decreased by back 
emf effect of the battery. To protect overcharging, a switching circuit will be used in our design.

### Constant current charging

* The uniform current will be supplied across the battery terminals which is in the opposite direction of 
its discharging direction. This is a fast-charging method. However, there is no way to avoid 
overcharging in this method. This major problem causes the battery to premature replacement. 

## Methodology

* We planned to develop a proper 24V, 8A lead acid battery charger. Therefore, we will use various steps 
for this project task. First, we will use PWM modulations techniques to produce constant PWM voltage 
through battery terminals. Also, we will use Darlington pair techniques to produce enough current 
through battery terminals. the switching circuit will be used to protect overcharging the battery. As this 
project, we will highly use analog electronics and power electronics components to fulfil this task. Also, 
we will plan to do good PCB and proper solid work designs for this project. We will initially use online 
circuit simulations tools to check our progress then availability we will use analog labs for testing 
purposes. Hope we will do this project in a good manner, and we will maintain proper timeline activities 
for this project.

## Block Diagram

![im1](https://user-images.githubusercontent.com/81348862/202192833-0d57108d-896b-488d-b74a-4b27c2163971.png)


* To charge the lead-acid battery from the AC source, initially AC source voltage is stepped down
using a step-down transformer, then use bridge rectifier circuit, filtering circuit and Voltage 
regulator to keep constant voltage. 24V DC voltage is obtained from the linear voltage 
regulator.
* Ramp waveform and PWM waveform are generated using Ramp generation circuit and 
comparator circuit. Pulse frequency is determined from Ramp duration. And in the switching 
circuit, the switching speed of the constant current supply is determined from the pulse duration 
of the PWM signal.
* Darlington pair is used to provide high current gain. This circuit provides 8A Constant current 
supply.
* The constant current will charge the battery up until it reaches the reference voltage.
* Then after the battery got the reference voltage the constant current mode will be switched to 
constant voltage mode.

## Basic circuit selection

For the Li-ion battery charging circuit we are in the basic need of
* PWM generation
* Constant voltage control
* Constant current control
To establish proper results, we may have to add additional circuitry.

### PWM generation

We need the PWM that have to have a variable duty cycle that we can control: to achieve this we took 
a triangular wave and compare the level with a varying voltage level and finally remove its negative 
part of the wave.
We are considering using a simple astable vibrator for triangular wave(near-approximation) 
generation and a comparator for PWM generation (with negative portion) and lastly, we are 
considering using an adder circuit for both amplification and to remove the negative part.

### Constant current control

Supplying a constant current to charge the battery is important. To accomplish this, we are considering 
using a PID like the approach that first measures the current and then by the error value we will 
manipulate the PWM.
We are considering using low-Side current measurement for the current measurement due to its 
inexpensiveness, simple circuit. We are trying to use a differential amplifying circuit to measure error 
values. After taking the error value we will apply this to an integrator circuit for Adjusting PWM signals. 
Integrator is used because the manipulation of PWM needs to be done due to accumulation of error 
rather than just by current instantaneous error.

### Constant voltage control

Just like current the voltage needs to be kept constant. The same kind of approach from current will 
be used for voltage control. That voltage will be controlled by adjusting to the error value.
First, we will measure the voltage by using a differential amplifying circuit then the error value will be 
calculated by another differential amplifying circuit and then this value will be sent to an integrator 
circuit. Here the last two methods that are used are exactly like in current control for the same 
reasoning.
The above details may change during the progress. The values that are selected are not according to 
the specifications.
The result will be created by combining the above results and adding further circuits for smoothening 
and tuning purposes.

### Testing Prototype

![im2](https://user-images.githubusercontent.com/81348862/202193419-660c5bba-6594-4218-8474-4919e5f1a2db.png)

