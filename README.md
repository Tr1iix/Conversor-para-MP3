# 🎧 Client-Side Audio to MP3 Converter

A fast, lightweight, and privacy-first web application that converts audio and video files directly into `.mp3` inside your browser — **no server uploads, no file limits, and zero tracking**.

🔗 **Live Demo:** [fancy-disk-21f7.nicoli-costa1612.workers.dev](https://fancy-disk-21f7.nicoli-costa1612.workers.dev/)

---

## ✨ Features

- **100% Client-Side Processing:** Files never leave your device. Decoding and MP3 encoding happen locally using the Web Audio API and WebAssembly/JS.
- **Batch Conversion:** Drag and drop multiple files at once and track real-time conversion progress per track.
- **Custom Bitrate Selection:** Choose between `96 kbps`, `128 kbps`, `192 kbps` (default), `256 kbps`, and `320 kbps`.
- **Bulk ZIP Download:** Download converted tracks individually or bundle all `.mp3` outputs into a single `.zip` archive (with automatic duplicate filename handling).
- **Broad Format Support:** Accepts any audio or video container supported by your browser (`M4A`, `AAC`, `WAV`, `OGG`, `FLAC`, `OPUS`, `WEBM`, `MP4`, `AIFF`, `CAF`, etc.).
- **Adaptive Dark/Light Theme:** Automatically respects system color-scheme preferences (`prefers-color-scheme`) with mobile safe-area support.

---

## 🛠️ Tech Stack & Architecture

- **Core:** Vanilla HTML5, CSS3 (CSS Custom Properties), and modern ES6+ JavaScript (single-file architecture, zero build step).
- **Audio Decoding:** Native browser `AudioContext.decodeAudioData()` (resamples and normalizes PCM float32 buffers to 16-bit signed integers, supporting mono and stereo).
- **MP3 Encoding:** [lamejs](https://github.com/zhuker/lamejs) (`v1.2.1`) — chunked encoding (`1152 * 32` samples per tick) to keep the UI responsive during large conversions.
- **Archiving:** [JSZip](https://stuk.github.io/jszip/) (`v3.10.1`) — generates uncompressed `.zip` blobs (`STORE` mode) instantaneously since MP3s are already compressed.
- **Hosting:** Deployed on **Cloudflare Workers**.

---

## 🚀 Running Locally

Because the entire application lives in a single self-contained `index.html` file with CDN dependencies, no bundler or package manager is required:

1. Clone the repository:
   ```bash
   git clone [https://github.com/Tr1iix/SEU-REPOSITORIO.git](https://github.com/Tr1iix/SEU-REPOSITORIO.git)
