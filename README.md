# 🎵 CYD Music Player

A premium, offline audio player designed for the **ESP32 CYD (Cheap Yellow Display)** featuring a 320x240 ILI9341 LCD, XPT2046 resistive touch digitizer, and a PCM5102A I2S DAC. Built with a gorgeous retro-futuristic **Synthwave visual style**, real-time spectrum visualizer, fluid slider scrubbing, and a thread-safe multi-core audio engine.

---

## 🚀 Installation & Flashing

The firmware is distributed as a compiled binary. You can flash it directly from your web browser using the Espressif Web Flasher, or download the binary offline.

<div align="center">
  <br>
  <a href="https://quadever-launcher.onrender.com/flasher?app=1784378076035" target="_blank">
    <img src="https://img.shields.io/badge/FLASH_FIRMWARE-Direct_Web_Flasher-cyan?style=for-the-badge&logo=espressif&logoColor=white&color=00f0ff" alt="Direct Web Flasher" height="50">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://quadever-launcher.onrender.com/apps/download/1784378076035" target="_blank">
    <img src="https://img.shields.io/badge/DOWNLOAD_BIN-Offline_Binary-purple?style=for-the-badge&logo=arduino&logoColor=white&color=780fdf" alt="Download Binary" height="50">
  </a>
  <br><br>
</div>

> [!IMPORTANT]
> **Touch Calibration is required right after flashing!**
> Upon first boot, navigate to **Settings** (bottom left), tap the **CAL** button, and follow the 4-corner crosshair wizard. Tap and hold each crosshair until it turns green to calibrate your resistive touch coordinates.

---

## ✨ Features

* 🎧 **Pulsing Boot Animation:** Features a 3-second animated vector headphones and flashing music note logo with bouncing equalizers.
* 🌅 **Synthwave Theme UI:** Responsive covers, persistent sidebar navigation, neon card outlines, and a 16-bar real-time visualizer.
* ⚡ **Multi-Core Thread Safety:** Dedicated background audio parsing on Core 0, leaving Core 1 isolated to render smooth UI animations and capture touch inputs at 60 FPS (separated via Mutex).
* 🎚️ **Fluid Drag Sliders:** Seek position, Master Volume, and Backlight Brightness adjust smoothly in real-time as you slide your finger.
* 🌓 **Color Inversion Toggle:** Easily toggle color inversion ON/OFF inside Settings to maintain compatibility across all CYD display variants.
* 💿 **100% Offline Music:** Recursively scans and parses local MP3/WAV files from your SD Card, eliminating radio buffering or loading lags.
* 🗃️ **Metadata Views:** Categorizes library tracks dynamically into Songs, Artists, Albums, Playlists, and Favorites.

---

## 🛠️ Hardware Requirements & Pinout

To output high-fidelity analog audio, you must connect a **PCM5102A I2S DAC** board to the CYD extension port:

| PCM5102A Pin | ESP32 CYD Pin / GPIO | Description |
| :--- | :--- | :--- |
| **BCK** | GPIO 4 | Bit Clock |
| **LRCK** | GPIO 22 | Left/Right Word Select Clock |
| **DIN** | GPIO 27 | Data Input |
| **GND** | GND | Ground |
| **VIN / VCC** | 3.3V or 5V | Power Supply |

*Note: Make sure to short the GND bridge pads on the PCM5102A board (SCK, FLT, DMP, FMT, BYP) to configure it for internal system clock operations.*

---

## 📁 SD Card Configuration

1. Format your Micro SD card to **FAT32** (sizes up to 32GB are supported).
2. Create a folder named `/music` at the root of the card.
3. Put your `.mp3` and `.wav` tracks directly inside `/music/`.
4. *Optional:* Arrange tracks into subdirectories like `/music/Artist/Album/Song.mp3` for automatic library categorization.

## 💖 Support My Work

If you love this project and want to support its continuation:

<div align="center">
  <br>
  <a href="https://www.quadever.com/support" target="_blank">
    <img src="https://img.shields.io/badge/SUPPORT_MY_WORK-Donate_/_Sponsor-red?style=for-the-badge&logo=githubsponsors&logoColor=white&color=ff007f" alt="Support My Work" height="50">
  </a>
  <br><br>
</div>
