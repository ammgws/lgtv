# lgtv - command line webOS remote for LGTVs

lgtv is a shell script utilizing websocat to communicate with the WebSocket of LGTVs.

## Requirements

* [websocat](https://github.com/vi/websocat)
* `wakeonlan` (optional)

## Configuration file

Default configuration file path:
```
~/.config/lgtv/config
```

Example config:
```
IP="192.168.0.12"
MAC="12:34:56:78:90:12"
KEY="abcdefghijklmnopqrstuvwxyz123456"
```

Generate a config file with:
```
lgtv auth <ip>
```

## Usage

```
lgtv - command line webOS remote for LGTVs

Usage: lgtv [-c <config>] <cmd> [<args>]

Get a client key:
  lgtv auth <ip>

Turn on TV:
  lgtv wakeonlan

Simple request:
  lgtv ssap://com.webos.service.update/getCurrentSWInformation

Request with payload:
  lgtv ssap://tv/openChannel {\"channelNumber\":\"2\"}

Request an input socket and send an input event:
  lgtv input "type:button\nname:INFO\n"

Pretty print JSON response:
  lgtv audio getStatus | grep response | python -m json.tool

Input examples:
  lgtv input button LEFT
  lgtv input button RIGHT
  lgtv input button DOWN
  lgtv input button UP
  lgtv input button HOME
  lgtv input button BACK
  lgtv input button ENTER
  lgtv input button DASH
  lgtv input button INFO
  lgtv input button 0
  lgtv input button 9
  lgtv input button ASTERISK
  lgtv input button CC
  lgtv input button EXIT
  lgtv input button MUTE
  lgtv input button RED
  lgtv input button GREEN
  lgtv input button BLUE
  lgtv input button VOLUMEUP
  lgtv input button VOLUMEDOWN
  lgtv input button CHANNELUP
  lgtv input button CHANNELDOWN
  lgtv input click
  lgtv input move 10 10 0
  lgtv input scroll 1 1

Request examples:
  lgtv api getServiceList
  lgtv audio volumeDown
  lgtv audio volumeUp
  lgtv audio getVolume
  lgtv audio getStatus
  lgtv audio setMute false
  lgtv audio setVolume 100
  lgtv com.webos.applicationManager getForegroundAppInfo
  lgtv com.webos.applicationManager launch com.webos.app.livetv
  lgtv com.webos.applicationManager listApps
  lgtv com.webos.applicationManager listLaunchPoints
  lgtv com.webos.service.ime deleteCharacters 5
  lgtv com.webos.service.ime insertText abc 0
  lgtv com.webos.service.ime sendEnterKey
  lgtv com.webos.service.update getCurrentSWInformation
  lgtv media.controls play
  lgtv media.controls pause
  lgtv media.controls stop
  lgtv media.controls rewind
  lgtv media.controls fastForward
  lgtv system turnOff
  lgtv system.launcher launch com.webos.app.livetv
  lgtv system.launcher close com.webos.app.livetv
  lgtv system.launcher open https://github.com
  lgtv system.notifications createToast "Hello World"
  lgtv tv channelDown
  lgtv tv channelUp
  lgtv tv getChannelList
  lgtv tv getChannelProgramInfo
  lgtv tv getCurrentChannel
  lgtv tv getExternalInputList
  lgtv tv openChannel 52
  lgtv tv switchInput HDMI_2
```
