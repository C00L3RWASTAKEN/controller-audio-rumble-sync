<p align="center">
  <a href="https://controller.oops.wtf">
    <img src="https://img.shields.io/badge/%E2%96%B6%20OPEN%20THE%20APP-controller.oops.wtf-5b4be0?style=for-the-badge&labelColor=151a26" alt="Open controller.oops.wtf" height="56">
  </a>
</p>

# Controller Audio Rumble Sync

Make your game controller vibrate in time with any audio file, right in your browser.

The audio is analyzed as it plays and split into two bands:

- **Bass** drives the left (heavy) motor
- **Treble** drives the right (light) motor

No install and no file conversion needed.

## Usage

1. Open the page in Chrome, Edge, Opera or Brave.
2. Press any button on your controller so the browser detects it.
3. Click **Test rumble** to check that the motors work.
4. Choose or drag in an audio file (MP3, WAV, OGG, M4A, FLAC, or anything your browser can play).

## Controls

| Control | What it does |
| --- | --- |
| Sensitivity | Higher reacts to quieter hits, lower reduces constant buzzing. |
| Audio delay | Delays the sound to match the controller's latency. Raise it if the rumble feels late. Wireless controllers usually need 50-150 ms. |

## Notes

- Rumble through the browser is not supported in Firefox or Safari (or maybe Safari does idk).
- Playback pauses if you switch tabs, and the motors are switched off when you pause, finish, refresh or close the page.
- Works on Windows, macOS and Linux, with Xbox controllers and many PlayStation controllers.

## How it works

1. Takes a spectrum of the audio many times per second.
2. Measures spectral flux (sudden increases in energy) in a bass band and a treble band to detect hits.
3. Turns those hits into 0-1 rumble levels with a short decay tail.
4. Sends the levels to the controller's two motors in real time using the browser's Gamepad API.

## Troubleshooting

- **Controller not detected:** make sure it's on and press a button on it. The browser won't see it until you do.
- **"Can't rumble it" message:** use Chrome or Edge.
- **Rumble out of sync:** adjust the audio delay. Wired controllers need less than Bluetooth ones.
- **No rumble at all:** try the Test rumble button. If that works but music doesn't, raise the sensitivity.

## Running locally

Download `index.html` or open the link in this repository.

## License

MIT
