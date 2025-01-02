---
sidebar_position: 1
---

# Adding custom buttons/toggles
1. In your project hierarchy under the `UI` section expand `Canvas > StatusBar > QuickSettings`
2. Now right click on `Buttons` and select `UI > SmartifyOS > More > Quick Settings > Button` or `UI > SmartifyOS > More > Quick Settings > Toggle` for a toggle
3. If you now select the new button you can set its icon and text in inspector tab (for a toggle you can add two icons)

## Custom Button/Toggle script
Right click in your project browser and click on `Create > SmartifyOS > More > Quick Settings Entry` and name the script.

### Button
For a button you need
```cs
using SmartifyOS.QuickSettings;

public class NewQuickSettingsEntry : BaseQuickSettingsEntry
{
    private void Start()
    {
        Init();
    }

    //Executed if this script is on a gameobject together with QuickSettings.Button component
    protected override void OnClick()
    {
        Debug.Log("Clicked");
    }
}
```

### Toggle
For a toggle you need

```cs
using SmartifyOS.QuickSettings;

public class NewQuickSettingsEntry : BaseQuickSettingsEntry
{
    private void Start()
    {
        Init();
    }

    //Executed if this script is on a gameobject together with QuickSettings.ToggleButton component
    protected override void OnToggleValueChanged(bool isOn)
    {
        Debug.Log("Toggled: " + isOn);
    }
}
```

You can also set the toggle

```cs
protected void SetToggle(bool isOn)
```