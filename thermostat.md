# Servo Thermometer Tutorial
## Make a Servo Activated Thermometer @showDialog
The servo rotates 0-180 depending on the weather
<div style="position:relative;height:0;padding-bottom:81.97%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---run?id=S91481-15981-53678-86740" allowfullscreen="allowfullscreen" sandbox="allow-popups allow-forms allow-scripts allow-same-origin" frameborder="0"></iframe></div>
## Step 1 - Set the servo to 0 degrees.
Drag the ``||pins:servoWritePin||`` block in to the ``||basic.Start||`` block.

Find the ``||pins:servoWritePin||`` Block in the ``||pins:pins||`` Folder.

```blocks
pins.servoWritePin(AnalogPin.P0, 0)
basic.forever(function () {
	
})
```
## Step 2 - Add the Temperature Sensor
Add a ``||basic.showNumber||`` block into the ``||basic.forever||`` loop.
Then add the ``||input.temperature||`` bubble into the ``||basic.showNumber||`` block.

```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
})
```

## Step 3 - Add Another Servo Write block

From the ``||pins:pins||`` folder add another ``||pins:servo write pin||`` block. 

```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
    pins.servoWritePin(AnalogPin.P0, 180)
})
```

## Step 4 - Add a Mapping Block from the Pins folder
Place the ``||pins.Mapping||`` bubble into the ``||pins:servoWritePin||`` block.

```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
    pins.servoWritePin(AnalogPin.P0, pins.map(
    
    ))
})

```

## Step 5 - Add a Mapping Block from the Pins folder
Next add another ``||input.temperature||`` bubble into the top line of the ``||pins.Mapping||`` block

FYI: We want **_MAP_** the temperature values from the sensor to the Servo values.
Enter **_-5_** and **_50_** for temperature values and **_0_** and **_180_** for degrees into the **Mapping** bubble as shown in the ``||hint bubble||``.


```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
    pins.servoWritePin(AnalogPin.P0, pins.map(
    input.temperature(),
    -5,
    50,
    0,
    180
    ))
})

```
## Final Step - Running the Program
When you play the program, adjust the temperature settings and note how the servo will respond to the temperature changes.
You have now just created a digital thermometer in degrees Celsius
