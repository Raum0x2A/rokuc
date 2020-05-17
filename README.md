# rokuc

### A cURL based roku remote for home automation

This bash script leverages cURL and roku's External Control Protocol ([ECP](https://developer.roku.com/docs/developer-program/debugging/external-control-api.md)), to aid in home automation.

## Usage :

rokuc -a [ADDRESS] [ [-h] [-v] [-c [ARGS]] [-l [ARGS]] ]

- -h                        Show help file

- -v                        Enable verbos

- -a [ADDRESS]    Ip address of roku device

- -c [ARGS]            Commands to Roku control
  
  - play, pause, |, p    Pause and play
  
  - home, #                  Home menu
  
  - select, ok, .             Select
  
  - vol+, v+, vup, +      Volume up
  
  - vol-, v-, vdown, -    Volume down
  
  - mute, m                  Mute
  
  - off, O                       Turn device off
  
  - on, I                         Turn device on
  
  - back, k                    Back
  
  - u, up                       Button Up
  
  - d, down                  Button Down
  
  - l, left                       Button Left
  
  - r, right                    Button Right
  
  - s.5                           Sleep 0.5sec
  
  - s1                            Sleep 1sec
  
  - s2                            Sleep 2sec
  
  - s5                            Sleep 5sec

- -l [ARGS]             Launch Channel
  
  - plex
  
  - youtube
  
  - netflix
  
  - hulu
  
  - tv
  
  - hdmi1
  
  - hdmi2
  
  - hdmi3
  
  - hdmi4
  
  - av1

### Usage Examples

Launch Netflix:

```bash
$> ./rokuc -a 192.168.1.142 -l nexflix
```

Pause/Play:

```bash
$> ./rokuc -a 192.168.1.142 -c pause
```

Multi command: Go home and turn volume down x2

```bash
$> ./rokuc -a 192.168.1.142 -c "# v- v-"
```

Launch plex, wait 5 seconds, move right, select:

```bash
$> /rokuc -a 192.168.11.142 -l plex -c "s5 > ."
```



###### Roku ECP documentation: [LINK](https://developer.roku.com/docs/developer-program/debugging/external-control-api.md)


