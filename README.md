# aiosenseme library

[![PyPI version](https://badge.fury.io/py/aiosenseme.svg)](https://badge.fury.io/py/aiosenseme) [![Downloads](https://pepy.tech/badge/aiosenseme)](https://pepy.tech/project/aiosenseme)

This branch of aiosenseme is intended to help test i6 fans which appears to not work like other SenseME fans.

## Command line access

To access a fan directly by ip address skipping the discovery step. Name must match the one you gave the fan in the Haiku app.

```console
$ aiosenseme --debug --name "Studio Beam Fan" --ip 172.20.3.39
DEBUG:aiosenseme.fan:Studio Beam Fan: Connecting
DEBUG:aiosenseme.fan:Studio Beam Fan: Connected
DEBUG:aiosenseme.fan:Studio Beam Fan: Status update
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SNSROCC;STATUS]='OCCUPIED'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [DEVICE;BEEPER]='ON'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [DEVICE;INDICATORS]='ON'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [DEVICE;LIGHT]='PRESENT'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [DEVICE;SERVER]='PRODUCTION'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [ERRORLOG;ENTRIES;NUM]='10'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [ERRORLOG;ENTRIES;MAX]='10'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;AUTO]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;DIR]='FWD'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;PWR]='ON'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;SPD;ACTUAL]='1'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;SPD;MAX]='7'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;SPD;MIN]='1'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;BOOKENDS]='1;7'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;TIMER;CURR]='0'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;TIMER;MAX]='7'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;TIMER;MIN]='1'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FAN;WHOOSH;STATUS]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FW;NAME]='FW000003'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [FW;FW000003]='2.5.0'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [GROUP;LIST]='Studio Fan'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [GROUP;ROOM;TYPE]='6'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LEARN;MAXSPEED]='7'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LEARN;MINSPEED]='0'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LEARN;ZEROTEMP]='2388'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;AUTO]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;LEVEL;ACTUAL]='0'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;BOOKENDS]='1;16'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;LEVEL;MAX]='16'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;LEVEL;MIN]='1'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [LIGHT;PWR]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NAME;VALUE]='Studio Beam Fan'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NW;AP;STATUS]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NW;DHCP]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NW;PARAMS;ACTUAL]='172.20.3.39;255.255.0.0;172.20.0.1'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NW;SSID]='Lawrence b'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [NW;TOKEN]='<redacted>'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SCHEDULE;CAP]='MAX EVENTS,29'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SCHEDULE;EVENT;LIST]='NONE'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SLEEP;EVENT;OFF]='LIGHT,PWR,OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SLEEP;EVENT]='ON'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SLEEP;STATE]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SMARTMODE;ACTUAL]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SMARTMODE;STATE]='OFF'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SMARTSLEEP;IDEALTEMP]='2111'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SMARTSLEEP;MAXSPEED]='7'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SMARTSLEEP;MINSPEED]='0'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SNSROCC;TIMEOUT;CURR]='660000'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SNSROCC;TIMEOUT;MAX]='86400000'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [SNSROCC;TIMEOUT;MIN]='60000'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [WINTERMODE;HEIGHT]='213'
DEBUG:aiosenseme.fan:Studio Beam Fan: Param updated: [WINTERMODE;STATE]='OFF'
```

This is what is looks like if an incorrect name is specified.

```console
$ aiosenseme --debug --name "Unknown Name" --ip 172.20.3.39
DEBUG:aiosenseme.fan:Unknown Name: Connecting
DEBUG:aiosenseme.fan:Unknown Name: Connected
DEBUG:aiosenseme.fan:Unknown Name: Status update
Unknown Name
  Model: Haiku Fan without light, FW Version: None
  IP Addr: 172.20.3.39, MAC Addr: 01:23:45:67:89:AB
  Token: None
State: Fan is off, Light is off, Whoosh: off
DEBUG:aiosenseme.fan:Unknown Name: Listener task cancelled
DEBUG:aiosenseme.fan:Unknown Name: Updater task cancelled
```

## Issues

* Do use this for anything other than testing i6 fans.
