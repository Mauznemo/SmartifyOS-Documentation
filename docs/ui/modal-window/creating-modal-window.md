---
sidebar_position: 2
---

# Creating a modal/dialog window

## Yes No modal
You can create modal windows with yes, no and other combinations like this

[ModalTypes](/docs/ui/modal-window/#modaltypes)
```cs
ModalWindow.Create().Init("Title", "Content", ModalWindow.ModalType.YesNo,
() => 
{ 
    Debug.Log("Pressed Yes");
},
() => 
{ 
    Debug.Log("Pressed No");	
});
```

## Custom button texts
You can also create a modal with custom texts on the buttons

```cs
ModalWindow.Create().Init("Title", "Content", "Custom Yes","Custom No",
() => 
{ 
    Debug.Log("Pressed Yes");
},
() =>
{
    Debug.Log("Pressed No");
});
```

## Updating a modal's content
After creating the modal you can still update it's content.

```cs
ModalWindow modalWindow = ModalWindow.Create();

modalWindow.Init("Test", "Hello", ModalWindow.ModalType.YesNo, () => { }, () => { });
```
You need to keep the `ModalWindow` in a variable to do this
```cs
modalWindow.UpdateContent("Hello World!");
```
