# 📡 Morse Communication Suite

A lightweight, browser-based Morse communication toolkit with a **Morse Beeper / Transmitter** and a **Morse Receiver** in one small standalone project.

The project is designed to run directly in a modern browser without a backend or build step.

## ✨ Features

### 📻 Morse Beeper / Transmitter
- Convert text to Morse code and transmit it as an audible telegraph-style tone.
- Manual Morse input using `.` and `-` buttons.
- Manual Morse keyboard entry with live decoding.
- Play controls: **Kirim**, **Pause**, and **Stop**.
- Optional **Repeat Mode**.
- Live character highlighting while a message is transmitted.
- Morse-code preview for the current message.
- **Real** and **Custom** modes.
- Custom controls for:
  - Speed: `5–40 WPM`
  - Frequency: `300–1200 Hz`
  - Volume: `1–50%`
- Built-in **Waveform** monitor.
- Built-in **Radio Waterfall** monitor with carrier marker and radio-style signal floor.
- **Download WAV** export for the Morse message.
- Uses the Web Audio API for tone generation.

### 🎙 Morse Receiver
- Receive Morse through the device microphone.
- Live audio waveform display.
- Live microphone level meter.
- **Radio-style Waterfall** / frequency visualization.
- Morse signal detection based on microphone level and optional tone filtering.
- Dot / dash duration detection.
- Automatic Morse decoding to text.
- Expected speed control: `5–40 WPM`.
- Microphone threshold control: `1–60%`.
- Tone filter modes: **Off**, **Low tone**, **Mid tone**, and **High tone**.
- Receiver log for signal/debug information.

## 🗂 Project Structure

```text
morse_suite/
├── index.html
├── morse_beeper.html
├── morse_receiver.html
└── README.md
```

### `index.html`
Landing page for opening the transmitter or receiver.

### `morse_beeper.html`
Standalone Morse transmitter with audio generation, waveform, waterfall, and WAV export.

### `morse_receiver.html`
Standalone microphone receiver with waveform, waterfall, signal detection, and Morse decoding.

## 🚀 Getting Started

No installation or build tools are required.

### Option 1 — Open locally

Download or clone the repository, then open:

```text
index.html
```

You can also open either HTML application directly:

```text
morse_beeper.html
morse_receiver.html
```

### Option 2 — Serve locally

For the best browser compatibility, especially for microphone access, serve the folder through a local HTTP server.

For example with Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

## 🎛 Beeper Usage

1. Open **Morse Beeper**.
2. Enter a message in **Ketik Pesan**.
3. Choose **Real** or **Custom** mode.
4. Press **▶ Kirim** to transmit.
5. Watch the **Waveform** and **Radio Waterfall** while the signal is active.
6. Use **Pause** or **Stop** as needed.
7. Press **⬇ Download WAV** to export the generated Morse audio.

### Real Mode

The current built-in Real preset uses:

```text
WPM:       20
Frequency: 700 Hz
Volume:    16%
```

In Real mode, these values are locked by the interface.

### Custom Mode

Custom mode enables the speed, frequency, and volume controls.

## 🎙 Receiver Usage

1. Open **Morse Receiver**.
2. Press **🎙 Start Receiver**.
3. Allow microphone permission when the browser asks.
4. Send an audible Morse tone close enough to the microphone.
5. Adjust **Expected Speed** to match the transmitter.
6. Adjust **Microphone Threshold** if the receiver is too sensitive or not sensitive enough.
7. Use **Tone Filter** when background noise makes detection difficult.
8. Monitor the waveform and waterfall while the receiver is listening.
9. Read the detected Morse and decoded message in the receiver panels.

## 📡 Visualizers

Both applications include radio-style visual monitoring:

```text
Waveform
───────────────
   ~~~~      ~~~~
 ~      ~  ~      ~

Waterfall
───────────────
noise  · · · · · ·
noise  · · █ · · ·
noise  · · █ · · ·
noise  · · █ · · ·
       frequency →
```

The Beeper visualizer represents the transmitter's carrier and signal state. The Receiver visualizer is driven by microphone audio analysis.

## 🔊 Audio Technology

The project uses browser-native **Web Audio API** components.

The Beeper generates a telegraph-style tone using a square oscillator, filtering, and quick gain attack/release. Morse timing is calculated from WPM using the standard 50-unit word timing model used by the application.

## 🎧 WAV Export

The Beeper includes browser-side WAV generation, so the exported audio does not require a server.

The downloaded file uses the generated Morse tone sequence and is saved as a `.wav` file.

## 🌐 Browser Requirements

A modern browser with Web Audio API support is recommended.

The Receiver additionally requires microphone access through `navigator.mediaDevices.getUserMedia()`.

For microphone use, browser security rules generally require a secure context such as **HTTPS** or **localhost**.

## 🧩 Dependencies

There are no external JavaScript packages or build dependencies in the current project.

Everything runs from the HTML files in the browser.

## ⚠️ Notes

- Receiver performance depends on microphone quality, speaker volume, room noise, and the selected threshold/filter settings.
- The Receiver is intended for audible Morse tones picked up by a microphone; it is not a direct RF modem.
- Waterfall displays are visual signal monitors and should not be interpreted as calibrated RF measurements.
- The transmitter and receiver are separate browser pages, but they can be used together on the same machine or across different devices.

## 🤝 Contributing

Suggestions, bug reports, UI improvements, decoder improvements, and visualization enhancements are welcome.

A simple contribution workflow:

```bash
git clone <your-repository-url>
cd <your-repository-folder>
# edit the HTML files
# test in a modern browser
git add .
git commit -m "Improve Morse suite"
git push
```

or
Live Demo 
https://bahrizalmulyawan.github.io/morse_suite/morse_beeper.html
## 📄 License

No license is currently specified in the project files. Add a `LICENSE` file and update this section when a license is chosen.
