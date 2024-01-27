# lgtv - command line webOS remote for LGTVs

lgtv is a shell script utilizing websocat to communicate with the WebSocket of LGTVs.

## Requirements

* [websocat](https://github.com/vi/websocat)
* `wakeonlan` (optional)

## Usage

```
lgtv - command line webOS remote for LGTVs

Usage: lgtv [-c <config>] <cmd> [<args>]

Run lgtv to get a list of examples
```

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
