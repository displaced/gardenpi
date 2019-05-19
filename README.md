# GardenPi

A Raspberry Pi Zero project to build an AirPlay and Bluetooth A2DP receiver for outdoor music.

## Goals

The goal is to have a RPi Zero running headless, acting as an AirPlay and Bluetooth A2DP receiver.  
The Pi will drive stereo unpowered speakers via an amplifier.  The Pi, Amp and power supply must be
contained within an IP65 (at a minimum) enclosure for continuous outdoor operation.

## Wanted Features

1. Play audio from AirPlay sources.
2. Play audio from Bluetooth A2DP sources.
3. Require a pre-defined PIN for Bluetooth clients to connect with.
4. Enforced ALSA-level maximum volume, with software volume for AirPlay/Bluetooth controlled by the client.
5. A new AirPlay streamer should replace an existing stream.
6. A new Bluetooth A2DP streamer should replace an existing stream.
7. Starting a new AirPlay stream should stop an existing Bluetooth stream.
8. Starting a new Bluetooth stream should stop an existing AirPlay stream.
9. Amplifier should be powered-down when not in use.

## Why not _Volumio_, _MusicBox_ or ...?

I gave Volumio, MusicBox and Moode a go.  In particular, Volumio has an excellent web interface, and
all of these also have some great features for local music, USB, Spotify, etc.  But I'm building my
own for a few reasons:

* I mainly want AirPlay so I can stream Apple Music from iOS/macOS devices.  But I'd like Bluetooth
  A2DP for non-Apple users.
* Pre-made distros either don't support A2DP without a fight, or make assumptions about how it should
  work (pairing method, etc).
* I've got no use for a full-featured web frontend, nor playback from local filesystems.

## Components

### Hardware

* A Raspberry Pi Zero W (built-in WiFi and Bluetooth radios)
* A HifiBerry AMP2 amplifier HAT
* A 120W, 18V Power Supply
* An IP65 enclosure

### Software

* Raspbian Stretch Lite (base OS)
* ALSA (core audio library, default in a fresh Stretch installation)
* shairport-sync (AirPlay receiver)
* bluealsa (Bluetooth A2DP)
* Scripts to hook it all up.
