---
sidebar_position: 1
---

# Serial Communication

To communicate with serial deices like Arduinos right click in the project browser in the place where you want to create the new script. Then click on `Create > SmartifyOS > Serial Communication Script`.
This will create a serial communication script for you.

Now you need to create a new empty object in your hierarchy (eg. right click on `Arduinos` and click on `Create Empty`) then you can just drag your script onto this object

## Manage existing Serial Communication Objects
To manage existing Serial Communication Objects and their scripts in your scene you can open the setting (`Ctrl + .` or `SmartifyOS > Settings`).
Then you can click on the tab `Communication`. There you can select the existing Serial Communication Objects in your scene and also remove them together with their script files.

## Base class: BaseSerialCommunication

### Init
```cs
portName = "COM1";
Init();
```
In `Start()` you have to call `Init()`, before calling it you can also set the serial port.

### ReadMessage
```cs
private void Update()
{
    ReadMessage();
}
```
In `Update()` you need to call `ReadMessage()`.

### Received
```cs
public override void Received(string message)
{
    
}
```
Called every time the serial device sends a message

### Send
```cs
Send("Hello World");
```
Send a message to the serial device