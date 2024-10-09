---
sidebar_position: 1
---

# Modal Window

## Class: ModalWindow
To create a modal window you need to use `SmartifyOS.UI`

### Create
```cs
public static ModalWindow Create()
```
Creates a new `ModalWindow`

| Returns         |                           |
| --------------- | ------------------------- |
| **ModalWindow** | The created `ModalWindow` |

### Init
```cs
public void Init(string title, string content, ModalType modalType, Action confirm, Action cancel)
```
Initializes the `ModalWindow` 

| Parameters    |                                             |
| ------------- | ------------------------------------------- |
| **title**     | Title of the window                         |
| **content**   | Text of the window                          |
| **modalType** | What type of modal this is                  |
| **confirm**   | Callback when the confirm button is pressed |
| **cancel**    | Callback when the cancel button is pressed  |

#### ModalTypes
| ModalTypes           |
| -------------------- |
| ModalType.Okay       |
| ModalType.OkayCancel |
| ModalType.YesNo      |
| ModalType.YesCancel  |

```cs
public void Init(string title, string content, string confirmText, string cancelText, Action confirm, Action cancel)
```

Initializes the `ModalWindow` with custom button texts

| Parameters      |                                             |
| --------------- | ------------------------------------------- |
| **title**       | Title of the window                         |
| **content**     | Text of the window                          |
| **confirmText** | Confirm button text                         |
| **cancelText**  | Cancel button text                          |
| **confirm**     | Callback when the confirm button is pressed |
| **cancel**      | Callback when the cancel button is pressed  |

### UpdateContent
```cs
public void UpdateContent(string content)
```

Updates the content of the `ModalWindow`

| Parameters  |                    |
| ----------- | ------------------ |
| **content** | New content string |

### Close
```cs
public void Close()
```
Closes the `ModalWindow`