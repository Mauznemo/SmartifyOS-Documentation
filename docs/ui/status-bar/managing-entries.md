---
sidebar_position: 1
---

# Managing entries
To add an icon to the status bar you need to use `SmartifyOS.StatusBar`.

## StatusBar

### AddStatus
```cs
public static StatusEntry AddStatus(Sprite sprite)
```
Create and add a new icon to the status bar.

| Parameters |                                                  |
| ---------- | ------------------------------------------------ |
| **sprite** | Sprite of the icon to be shown in the status bar |

| Returns         |                               |
| --------------- | ----------------------------- |
| **StatusEntry** | The newly created StatusEntry |

## StatusEntry

### Show
```cs
public void Show()
```
Shows the status entry

### Hide
```cs
public void Hide()
```
Hides the status entry

### Remove
```cs
public void Remove()
```
Removes the status entry

## Example
```cs
using SmartifyOS.StatusBar;

public class StatusBarExample : MonoBehaviour
{
    [SerializeField] private Sprite iconSprite;

    private StatusBar.StatusEntry entry;

    private void Start()
    {
        entry = StatusBar.AddStatus(iconSprite);
        entry.Hide(); //Optionally hide on start
    }

    //Some function to show the status icon
    public void Show()
    {
        entry.Show();
    }

    //Some function to hide the status icon
    public void Hide()
    {
        entry.Hide();
    }
}
```