# aiosenseme library

[![PyPI version](https://badge.fury.io/py/aiosenseme.svg)](https://badge.fury.io/py/aiosenseme) [![Downloads](https://pepy.tech/badge/aiosenseme)](https://pepy.tech/project/aiosenseme)

This branch of aiosenseme is intended to help test i6 fans which appears to not work like other SenseME fans.

## Command line access

To access a fan directly by ip address skipping the discovery step. Name must match the one you gave the fan in the Haiku app.

```console
$ aiosenseme --name "Studio Beam Fan" --ip 172.20.3.39
Studio Beam Fan
  Room Name: Studio Fans, Room Type: Family Room
  Model: Haiku Fan with light, FW Version: 2.5.0
  IP Addr: 192.168.1.2, MAC Addr: FF:FF:FF:FF:FF:FF
  Token: 73264cb2-1234-1234-1234-012345678912
State: Fan is on (speed: 2), Light is off, Whoosh: off
```

## Issues

* Do use this for anything other than testing i6 fans.
