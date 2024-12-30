---
sidebar_position: 2
---
# Creating a custom window script
Right click in your project browser and click on `Create > SmartifyOS > UI Window Script` and open it up (remember to drag the new script onto the new game object).

## Base class: BaseUIWindow

### wasOpen
```cs
protected bool wasOpen
```
Was the window open before it was closed by another window (Is `true` if the window was closed with `Hide(true)`)

### isOpen
```cs
protected bool isOpen
```
Is the window currently open

### Init
```cs
protected void Init()
```
Needs to be called in `Start()` to initialize everything

### HandleWindowOpened
```cs
protected virtual void HandleWindowOpened(BaseUIWindow window)
```

Called when any other window is opened

| Parameters |                            |
| ---------- | -------------------------- |
| **window** | The window that was opened |

You can use this to hide a window is another one opens
#### Example:
```cs
protected override void HandleWindowOpened(BaseUIWindow window)
{
    //Add all windows that should hide this window when they open
    if (window.IsWindowOfType(typeof(UIWindow1), typeof(UIWindow2)))
    {
        Hide(true);
    }
}
```

### HandleWindowClosed
```cs
protected virtual void HandleWindowClosed(BaseUIWindow window)
```
Called when any other window is closed

| Parameters |                            |
| ---------- | -------------------------- |
| **window** | The window that was closed |

You can use this to re-open your window after it was closed by another
#### Example:
```cs
protected override void HandleWindowClosed(BaseUIWindow window)
{
    if(!wasOpen) { return; }

    //Add all windows that should trigger this window to reopen when they close
    if (window.IsWindowOfType(typeof(UIWindow1), typeof(UIWindow2)))
    {
        Show();
    }
}
```

### OnShow
```cs
protected virtual void OnShow()
```
Called when the window is shown (opened)

### OnHide
```cs
protected virtual void OnHide()
```
Called when the window is hidden (closed)

### Show
```cs
public void Show()
```
Shows the window

### Hide
```cs
public void Hide(bool internalUpdate = false)
```
Hides the window

| Parameters                             |                                       |
| -------------------------------------- | ------------------------------------- |
| **internalUpdate** (default = `false`) | `wasOpen` will not be reset if `true` |