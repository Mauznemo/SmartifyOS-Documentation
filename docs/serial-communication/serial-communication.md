---
sidebar_position: 1
---

# Serial Communication

To communicate with serial deices like Arduinos right click in the project browser in the place where you want to create the new script. Then click on `Create > SmartifyOS > Serial Communication Script`.

This will create a serial communication script for you.

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