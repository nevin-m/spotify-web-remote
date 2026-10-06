# Spotify Web Remote

A lightweight, single-file web-based Spotify remote that lets you control playback from a browser.

The interface combines a now-playing display with physical-style controls, including a rotary volume knob, playback buttons, seeking, shuffle, and repeat.

![Spotify Web Remote](https://i.imgur.com/yfHhtxx.png)

## Demo

**[▶ Live Demo](https://nevin-m.github.io/spotify-web-remote/index.html)**

Try the interface directly in your browser. The built-in demo mode works without connecting a Spotify account.

## Features

- View currently playing track
- Display album artwork
- Play / pause
- Skip to the next track
- Go to the previous track
- Rotary volume control
- Seek through the current track
- Toggle shuffle
- Change repeat mode
- Touch-friendly interface
- Keyboard shortcuts
- Shows the active Spotify device
- Interface adapts its background to the album artwork
- Built-in demo mode
- Uses Spotify Authorization Code with PKCE
- No backend required
- Entire application is contained in a single HTML file

## Use Cases

### Dedicated Desk Music Controller

One of the main ideas behind this project is using it as a dedicated music controller on your desk.

You can run the web app on a small touchscreen computer and keep it next to your monitor. This gives you a dedicated Spotify control panel without needing to pick up your phone or switch applications.

You can quickly:

- Play and pause music
- Skip tracks
- Adjust volume using the on-screen knob
- Seek through a song
- Toggle shuffle
- Change repeat mode
- See what's currently playing
- See which Spotify device is active

For example, you could use a small Raspberry Pi or another touchscreen computer with a display, run the remote in fullscreen, and turn it into a dedicated Spotify controller.

### Other Uses

The project can also be used as:

- A phone or tablet Spotify remote
- A secondary control screen for a computer
- A wall-mounted music controller
- A DIY touchscreen music controller
- A simple local Spotify control panel

## Requirements

- A Spotify account
- **Spotify Premium** for playback control
- A Spotify Developer application
- A modern web browser
- Python 3 for the easiest local setup

## Setup

### 1. Create a Spotify Developer Application

Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard) and create an application.

Copy the application's **Client ID**.

You do **not** need to put your Spotify Client Secret into this project.

### 2. Configure the Redirect URI

The Redirect URI must exactly match the address you use to open the application.

For example, if you run the project locally using port `8888`:

```text
http://127.0.0.1:8888/spotify-remote.html
