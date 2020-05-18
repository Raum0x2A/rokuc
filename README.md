# rokuc

### A cURL based roku remote for home automation

This bash script leverages cURL and roku's External Control Protocol ([ECP](https://developer.roku.com/docs/developer-program/debugging/external-control-api.md)), to aid in home automation.

## Usage :

```
Send simple remote commands to Roku devices using curl to interact with Rokus ECP (External Control Protocal) server on port 8060.

Usage: rokuc [[-a [ADDRESS]] [-s]] [[-h] [-v] [-c [ARGS]] [-l [ARGS]] ]
   -a | --address                  IP address of roku device ** REQUIRED **
   -c | --command                  Send remote commands to device
   -l | --launch                   Launch Channel/Application on device
   -v | --verbose                  Enable verbose mode
   -h | --help                     Display this message
   -i | --version		   Display version info and exit
   -s | --scan	 		   Scan LAN for active Roku devices


Args for [-c|--command] flag
   play | pause | | | p            Pause and Play
   home | #                        Go to home screen
   select | ok | .                 Select
   vol+ | v+ | vup | +             Turn volume up
   vol- | v- | vdown | -           Turn volume down
   mute | m                        Mute
   off | power-off | shutdown | O  Power off Roku TV
   on | power-on | startup | I     Power on Roku TV
   back | k                        Back
   u | up | ^                      Up arrow
   d | down | v                    Down arrow
   l | left | <                    Left arrow
   r | right | >                   Right arrow
   s.5                             Wait 0.5 seconds
   s1                              Wait 1 second
   s2                              Wait 2 seconds
   s5                              Wait 5 seconds

Args for [-l|--launch] flag
   plex      Launch Plex.tv
   youtube   Launch YouTube 
   netflix   Launch Netflix
   hulu      Launch Hulu
   tv        Launch Digital TV on Roku TVs
   hdmi1     Launch HDMI1
   hdmi2     Launch HDMI2
   hdmi3     Launch HDMI3
   hdmi4     Launch HDMI4
   av1       Launch AV1

```
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
$> ./rokuc -a 192.168.11.142 -l plex -c "s5 > ."
```

Scan network for devices 

```bash
$> ./rokuc -s 192.168.0.0
```



###### Roku ECP documentation: [LINK](https://developer.roku.com/docs/developer-program/debugging/external-control-api.md)


