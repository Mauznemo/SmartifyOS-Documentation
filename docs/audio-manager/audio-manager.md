---
sidebar_position: 2
---

# Audio Manager
To play sounds or set the system volume you need to use `SmartifyOS.Audio`.

## AudioManager

### audioConfig_SO
The `AudioConfig_SO` ScriptableObject.

### PlaySound
```cs
public void PlaySound(AudioClip audioClip)
```
Lets you play any audio clip.

### SetSystemVolumeWithOverlay
```cs
public async Task SetSystemVolumeWithOverlay(float volume)
```
Sets the system output volume in percentage with an UI overlay, useful for external audio control like a hardware audio control nob.

### SetSystemVolume
```cs
public async Task SetSystemVolume(float volume)
```
Sets the system output volume in percentage

### GetSystemVolume
```cs
public float GetSystemVolume()
```
Returns the system output volume in percentage.
