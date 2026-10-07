# Spotify Web Remote

A lightweight, single-file web-based Spotify remote that lets you control playback from a browser.

The interface combines a now-playing display with physical-style controls, including a rotary volume knob, playback buttons, seeking, shuffle, and repeat.

![Spotify Web Remote](https://i.imgur.com/yfHhtxx.png)

## Demo

**[▶ Live Demo](https://nevin-m.github.io/spotify-web-remote/spotify-remote.html)**

If you want to use the demo, Redirect URL in spotify dash should be "https://nevin-m.github.io/spotify-web-remote/index.html"

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
```

Add that exact URL as a Redirect URI in your Spotify Developer application.

The application also displays the Redirect URI it is currently using on the setup screen.

### 3. Download or Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/spotify-web-remote.git
cd spotify-web-remote
```

### 4. Start a Local Web Server

You cannot simply double-click the HTML file because Spotify OAuth requires the page to be served through HTTP/HTTPS.

With Python 3:

```bash
python3 -m http.server 8888
```

On Windows:

```powershell
py -m http.server 8888
```

Then open:

```text
http://127.0.0.1:8888/spotify-remote.html
```

### 5. Connect Spotify

1. Enter your Spotify **Client ID**
2. Click **Connect Spotify**
3. Sign in to Spotify
4. Authorize the application
5. Start playing something on Spotify

The remote should then display your current playback.

## Controls

### Touch / Mouse

| Control | Action |
|---|---|
| Volume knob | Rotate to change volume |
| Click volume knob | Play / pause |
| Progress bar | Click to seek |
| ⏮ | Previous track |
| ⏭ | Next track |
| Shuffle | Toggle shuffle |
| Repeat | Cycle through repeat modes |
| Disconnect | Disconnect the current Spotify session |

The volume knob also supports mouse-wheel scrolling.

### Keyboard

| Key | Action |
|---|---|
| `Space` | Play / pause |
| `←` | Previous track |
| `→` | Next track |
| `↑` | Increase volume |
| `↓` | Decrease volume |

Keyboard shortcuts are disabled while typing in the Client ID field.

## Spotify Permissions

The application requests:

```text
user-read-playback-state
user-modify-playback-state
user-read-currently-playing
```

These permissions allow the application to:

- Read the current playback state
- Read the currently playing track
- Control Spotify playback

## Spotify Premium

Spotify playback control requires a **Spotify Premium** account.

If Spotify returns a `403` error when attempting to control playback, make sure the account being used has Premium and that the Spotify application is configured correctly.

You also need to have an active Spotify playback device for playback commands to work.

## Security

This project uses **Authorization Code with PKCE** for authentication.

The Spotify Client Secret is not required and should **not** be placed in the HTML file.

Authentication information is stored locally in the browser.

### Important

Never commit the following to GitHub:

- Spotify Client Secrets
- Personal access tokens
- Refresh tokens
- Other private credentials

Each person using the project should create and use their own Spotify Developer application and Client ID.

## GitHub Pages

The project can also be hosted using GitHub Pages.

If you use GitHub Pages, add your GitHub Pages URL as a Redirect URI in your Spotify Developer application.

For example:

```text
https://YOUR_USERNAME.github.io/spotify-web-remote/spotify-remote.html
```

Then open the GitHub Pages version of the application and enter your Spotify Client ID.

## Project Structure

```text
├── spotify-remote.html
└── README.md
```

There is no:

- Node.js setup
- npm installation
- Build process
- Backend
- Database
- Frontend framework

Everything required for the application is contained in `spotify-remote.html`.

## How It Works

The application runs entirely in the browser.

It communicates directly with the Spotify Web API and uses Spotify's OAuth authorization flow with PKCE.

```text
Browser
   │
   ├── Spotify Login
   │
   ▼
Spotify Authorization
   │
   ▼
Access Token
   │
   ▼
Spotify Web API
   │
   ├── Current playback
   ├── Play / pause
   ├── Next / previous
   ├── Volume
   ├── Seeking
   ├── Shuffle
   └── Repeat
```

No personal Spotify data needs to pass through a server operated by this project.

## Technology

Built using:

- HTML
- CSS
- Vanilla JavaScript
- Spotify Web API
- Spotify OAuth Authorization Code + PKCE
- Canvas API
- Browser Local Storage

No external frontend framework is required.

## License

This project is open source. You are free to modify it for your own projects.

If you redistribute or modify the project, consider keeping the original project attribution.

---

## Disclaimer

This project is an independent third-party project and is not affiliated with or endorsed by Spotify.

Spotify and the Spotify logo are trademarks of Spotify AB.
