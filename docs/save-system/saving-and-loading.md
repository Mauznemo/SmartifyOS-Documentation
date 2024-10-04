---
sidebar_position: 1
---

# Saving and Loading
To save and load data you have to use `SmartifyOS.SaveSystem`

## Loading
To for example load the saved audio volume.
```cs
value = SaveManager.Load().system.audioVolume
```

## Saving
And to save a new value you can just do.
```cs
SaveManager.Load().system.audioVolume = value
```
There is **no** need to call `SaveManager.Save()` afterwards.