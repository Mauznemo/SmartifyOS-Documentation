---
sidebar_position: 1
---

# Playing sounds
To play sounds you need to use `SmartifyOS.Audio`.
Then you can simply call

```cs
AudioManager.Instance.PlaySound(audioClip);
```
Or this, if the file is in `AudioManager.audioConfig_SO`
```cs
AudioManager.Instance.PlaySound(AudioManager.audioConfig_SO.notificationSounds.info);
```

## Adding audio files to `AudioManager.audioConfig_SO`
To add an audio file to the config right click in your project browser `Create > SmartifyOS > Audio > Add Audio Config`, name the file and open it.
\
In there you can add new AudioClip variables and optionally structs
```cs
using UnityEngine;

namespace SmartifyOS.Audio
{
    public partial class AudioConfig_SO : ScriptableObject
    {
        public WarningSounds warningSounds;
    }

    [System.Serializable]
    public struct WarningSounds
    {
        public AudioClip parkingBrakeOn;
        public AudioClip doorOpen;
    }
}
```

Now assign the audio files:
1. Import the audio file into Unity
2. Click on the scriptable object `Assets/ScriptableObjects/AudioConfigSO`
3. In the inspector window you should be able to assign the audio files.
   ![](/img/audio-config-so.png)