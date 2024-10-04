---
sidebar_position: 1
---

# Sending Notifications
To send a notification you need to use `SmartifyOS.Notifications`.

Then you can just do
```cs
NotificationManager.SendNotification(NotificationType.Info, "Hello World!");
```

## NotificationManager

### SendNotification

```cs
public static void SendNotification(NotificationType notificationType, string text, bool mute = false, float showTime = 5f)
```
Sends a new on screen notification

| Parameters           |                                                       |
| -------------------- | ----------------------------------------------------- |
| **notificationType** | Changes the color, sound and icon of the notification |
| **text**             | Text of the notification                              |
| **mute**             | If the notification should be muted                   |
| **showTime**         | Time in seconds to show the notification              |

#### NotificationTypes
| NotificationTypes        |
| ------------------------ |
| NotificationType.Info    |
| NotificationType.Warning |
| NotificationType.Error   |