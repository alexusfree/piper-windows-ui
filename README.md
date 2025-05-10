# SUZA Voice Studio

<div align="center">
  <a href="https://suzagear.com/voicestudio">
    <img src="https://img.shields.io/badge/Download-One%20Click%20Installer-brightgreen?style=for-the-badge" alt="Download One-Click Installer" />
  </a>
</div>

SUZA Voice Studio is a powerful, elegant offline text-to-speech application based on the Piper TTS engine. Generate natural-sounding speech with 29+ AI voices without requiring an internet connection.

## Features

- **Completely Offline**: No internet connection required, 100% privacy
- **29+ Neural Voices**: High-quality AI voices in US and UK English
- **Modern UI**: Sleek, intuitive interface with a dark theme
- **Free & Open Source**: No usage limits, no API costs

## Installation Options

### Option 1: One-Click Installer (Recommended)

Download the ready-to-use installer from our website:

🔗 [Download SUZA Voice Studio Installer](https://suzagear.com/voicestudio)

The installer version:
- Comes pre-bundled with all dependencies
- Installs to user directory (no admin rights needed)
- Creates desktop and start menu shortcuts

### Option 2: Run from Source

To run SUZA Voice Studio from source:

1. Clone this repository
   ```
   git clone https://github.com/yourusername/suza-voice-studio.git
   cd suza-voice-studio
   ```

2. Install dependencies
   ```
   pip install -r requirements.txt
   ```

3. Run the application
   ```
   python suza_voice_studio_wrapper.py
   ```

## Building Your Own Installer

If you want to build your own installer:

1. Run the build script
   ```
   python build_installer.py
   ```

2. Use Inno Setup to compile the installer
   ```
   "C:\Program Files (x86)\Inno Setup 6\ISCC.exe" SUZAVoiceStudio.iss
   ```

See [BUILD.md](BUILD.md) for detailed build instructions.

## Usage

1. Select a voice from the dropdown menu
2. Type or paste your text
3. Adjust speed, pitch, and emotion if desired
4. Click "Generate" to create speech
5. Play, save, or export the generated audio

Voice models are downloaded automatically the first time you use a voice.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgements

- Based on the [Piper TTS](https://github.com/rhasspy/piper) engine
- Voices trained on open datasets

## Directory Structure

```
SUZA_Voice_Studio/
├── suza_voice_studio.py   # Main application
├── download_samples.py    # Utility to download all voice samples
├── requirements.txt       # Python dependencies
├── icon.png               # Application icon
├── models/                # Downloaded voice models
│   ├── en_US/             # US English voices
│   └── en_GB/             # UK English voices
├── configs/               # Voice configuration files
├── samples/               # Voice sample files
├── output/                # Generated audio files
└── piper_win/             # Piper executable
    └── piper.exe
```

## Notes

- Voice models are downloaded on-demand when first selected
- Generated audio files are saved in the output folder with names based on the text content
- Voice samples help you choose a voice before downloading the full model
- The "Download All Models" feature requires substantial disk space (multiple GB)

## Creating an EXE

To create a standalone executable file:

1. Install PyInstaller:
   ```
   pip install pyinstaller
   ```

2. Create the executable:
   ```
   pyinstaller --onefile --windowed --icon=icon.png suza_voice_studio.py
   ```

3. Copy the required folders to the `dist` directory:
   - `piper_win`
   - `models`
   - `configs`
   - `samples`
   - `output`

## Credits

This application uses the [Piper TTS engine](https://github.com/rhasspy/piper) for speech synthesis. 