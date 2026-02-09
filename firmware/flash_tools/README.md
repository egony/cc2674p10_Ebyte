# Flash tool for cc2652p1/cc2652p7/cc2674p10 chips

## Description

Just a ptoof of concept, so it is early alpha version.

This is the fork of https://github.com/TexasInstruments/simplelink-lowpower-f2-sdk/tree/main/source/third_party/cc2538-bsl

Into this fork some code injected from https://github.com/smlight-tech/smlight-cc-flasher

### Requires

Download and install [python 3.13](https://www.python.org/downloads/) or later.

Install necessary add-ons:

    pip install pyserial
    pip install intelhex

### Usage example

    python ti-python-sbl.py -d CC26X4 -p COM3 -ewv znp_CC2674P10_E72_20260101.hex
    python ti-python-sbl.py -d CC26X4 -p socket://192.266.3.200:6638 -b 115200 -ewv znp_CC2674P10_E72_20260101.hex

## Changelog

### 2026-01-11

- initial early alpha release
- magic support removed (because useless)
- .bin files support damaged, will fix later maybe
- erase-write mode damaged (yes, you need no this), will fix later maybe
- packet buffer increased to 252
- socket mode speedups
