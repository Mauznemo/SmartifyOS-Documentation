---
sidebar_position: 2
---

# Adding content to page

### Adding a button
Right click on the new page game object and then on `UI > SmartifyOS > More > Settings > Button`, set the text and [set the icon](#setting-the-icon)

### Adding a link button
Right click on the new page game object and then on `UI > SmartifyOS > More > Settings > Link Button`, set the text and [set the icon](#setting-the-icon).

Drag any settings page you want to open into the `Page to Open` field

### Adding an input field
Right click on the new page game object and then on `UI > SmartifyOS > More > Settings > InputField`, set the label, paceholder and [set the icon](#setting-the-icon) (and optionally the text).

### Adding a toggle 
Right click on the new page game object and then on `UI > SmartifyOS > More > Settings > Toggle`, set the text and and set the icon by changing `Icon Source`.

#### Setting the icon
To set an icon double click on the `Icon` selection filed (this will select the image in the inspector), now you can select a sprite as the source image

## Creating the page's script
After creating the page you also need to create a script for it.

1. Right click in your project browser and click on `Create > SmartifyOS > More > Settings Page`
2. Drag the newly created script onto the new page game object
3. In the inspector input the page name
4. Now open the script up

Here is an example script:

```cs
using UnityEngine;

namespace SmartifyOS.Settings
{
    public class NewSettingsPage : BaseSettingsPage
    {
        [SerializeField] private ToggleButton toggleButton;
        [SerializeField] private Button button;
        [SerializeField] private InputField inputField;

        private void Awake()
        {
            toggleButton.onValueChanged += (value) =>
            {
                Debug.Log("Toggled: " + value);
            };

            button.onClick += () =>
            {
                Debug.Log("Clicked");
            };

            inputField.onValueChanged += (value) =>
            {
                Debug.Log("Input: " + value);
            };
        }

        protected override void OnOpened()
        {
            Debug.Log("Settings Page opened");
        }
    }
}
```

You can also open the settings page from itself with

```cs
public void Open()
```
