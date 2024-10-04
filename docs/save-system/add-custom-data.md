---
sidebar_position: 2
---

# Adding custom data
For adding custom data to the save system you can right click in you project browser `Create > SmartifyOS > Save System > Add Save Data`, give the file a name and open it.


In the partial class you can add variables you want to add.

```cs
public partial class SaveData
{
   //Add your custom variables here (public)
}
```

## Example:
```cs
namespace SmartifyOS.SaveSystem
{
   public partial class SaveData
   {
      public LightController lightController;
   }

   public struct LiveController
   {
      public string arduinoPort;
   }
}
```
\
Now you can load and save it just like all other save data.

\
For loading:
```cs
portName = SaveManager.Load().liveController.arduinoPort;
```

For saving:
```cs
SaveManager.Load().liveController.arduinoPort = value
```

## Adding data to SaveData.system
If you want to add custom data to `SaveData.system` you can just do:

```cs
namespace SmartifyOS.SaveSystem
{
   public partial class System
   {
      //Add your custom variables here (public)
   }
}
```