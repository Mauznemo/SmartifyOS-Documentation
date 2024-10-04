---
sidebar_position: 1
---

# System Events

To communicate with external programs like python scrips you can use `SystemEventManager` in `SmartifyOS.SystemEvents`

## SystemEventManager

System event manager for communicating with external processes using file changes.

### CallEvent
```cs
public static void CallEvent(string eventPath, string content, bool createIfNotExists = false)
```
Modifies the file to trigger a change.

| Parameters            |                                                                                   |
| --------------------- | --------------------------------------------------------------------------------- |
| **eventPath**         | Path to file, relative to user profile (eg. `SmartifyOS/Events/event`)            |
| **content**           | Content to write in file to add additional data for the other script (eg. python) |
| **createIfNotExists** | Should the file be created if it doesn't exist                                    |

### SubscribeToEvent
```cs
public static void SubscribeToEvent(string eventPath, Action<string> onEvent)
```
Subscribes to file changes

| Parameters    |                                                                        |
| ------------- | ---------------------------------------------------------------------- |
| **eventPath** | Path to file, relative to user profile (eg. `SmartifyOS/Events/event`) |
| **onEvent**   | Called when the file changes, includes the files content as string     |

**Usage Example:**
```cs
private void Start()
{
   SystemEventManager.SubscribeToEvent("SmartifyOS/Events/OnUsbDeviceConnected", OnUsbDeviceConnected);
}

private void OnUsbDeviceConnected(string content)
{
   Debug.Log("USB device connected");
}
```