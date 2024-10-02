---
sidebar_position: 2
---

# Live Serial Communication
To communicate with serial deices like Arduinos and receive messages in realtime right click in the project browser in the place where you want to create the new script. Then click on `Create > SmartifyOS > Live Serial Communication Script`.

## Difference to normal Serial Communication Script
If you for example have an Arduino that is constantly sending data (like in `loop()` with no or little delay) the normal Serial Communication Script will get delayed more and more over time and lag out the entire application.

The Live Serial Communication Script reads the messages on another thread so that it wont slow down the application.

## Base class: BaseLiveSerialCommunication

### InitLive
```cs
portName = "COM1";
InitLive();
```
In `Start()` you have to call `InitLive()`, before calling it you can also set the serial port.

### StopSerialThread
```cs
private void OnDestroy()
{
    StopSerialThread();
}
```
In `OnDestroy()` you need to call `StopSerialThread()` to stop the thread.

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