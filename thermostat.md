# Servo Thermometer Tutorial


## Step 1 - Begin by setting servo at 0 degrees
Drag the ``||pins:servoWritePin||`` block in to the ``||basic.Start||``.

Find the **Servo Write Pin** Block in the **Pins** Folder.

```blocks
pins.servoWritePin(AnalogPin.P0, 0)
basic.forever(function () {
	
})
```
## Step 2 - Add the Temperature Sensor to the **Forever** block
Add a **show number** block into the **forever loop**.
Then add the **temperature (C)** bubble into the **show number** block

```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
})
```

## Step 3 - Add Another Servo Write block

From the **Pins** folder add another **Servo Write Pin** block 
```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
    pins.servoWritePin(AnalogPin.P0, 180)
})
```

## Step 4 - Add a Mapping Block from the Pins folder
Place the **Mapping** bubble into the **Servo Write Pin** block.

Next **duplicate** the **_temperature_** bubble and place it into the top line of the **_mapping_** block

FYI: We want **_MAP_** the temperature values from the sensor to the Servo values.
Enter **_-5_** and **_50_** for temperature values and **_0_** and **_180_** for degrees into the **Mapping** bubble.


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