# Nuclear Option - MFD Video Player

Play custom videos and stream YouTube/Twitch on your cockpit MFD screens. Drop video files into the plugin folder, or enter a URL to stream live content on your tactical displays.

![BepInEx](https://img.shields.io/badge/BepInEx-5.x-blue) ![Game](https://img.shields.io/badge/Nuclear%20Option-Steam-black)

## Requirements

- [Nuclear Option](https://store.steampowered.com/app/2296550/Nuclear_Option/) on Steam
- [BepInEx 5.x](https://github.com/BepInEx/BepInEx/releases) (Unity Mono)

### Optional (for URL streaming)

- [yt-dlp.exe](https://github.com/yt-dlp/yt-dlp/releases) - Place in plugins folder or PATH
- [ffmpeg.exe](https://ffmpeg.org/download.html) - Required for Twitch live streams. Place in plugins folder or PATH

## Installation

1. Install BepInEx 5.x into your Nuclear Option game folder
2. Run the game once to generate the BepInEx folder structure
3. Copy `MFDVideoPlayer.dll` into `[Game Folder]\BepInEx\plugins\`
4. (Optional) Place video files (`.mp4`, `.webm`, `.avi`, `.mov`) in the same `plugins` folder
5. (Optional) Place `yt-dlp.exe` and `ffmpeg.exe` in the `plugins` folder for URL streaming
6. Launch the game

## Controls

| Key | Function |
|-----|----------|
| `F11` | Toggle video playback on/off |
| `Page Up` | Next video (local files only) |
| `Page Down` | Previous video (local files only) |
| `+` | Volume up |
| `-` | Volume down |

## Features

### Local File Playback
- Plays video files on all cockpit MFD/tactical screens
- Supports multiple video files with switching
- Per-screen selection (play on all screens or a specific one)

### URL Streaming (v2.0.0)
- **YouTube**: Paste any YouTube URL to stream on MFD
- **Twitch Live**: Watch Twitch live streams on your cockpit screens
- **Other sites**: Any URL supported by yt-dlp
- Twitch live streams use segment-based capture with double-buffering for continuous playback
- Source selection UI: choose between local files or URL input

### General
- Adjustable volume
- Loop playback (configurable, local files)
- On-screen HUD showing source type, current time, and controls
- Per-screen or all-screen targeting
- Stopping playback restores the original radar display

## How URL Streaming Works

1. Press `F11` in cockpit → Select `[2] Stream URL`
2. Paste a YouTube or Twitch URL → Press Enter
3. **YouTube**: yt-dlp resolves the direct video URL, plays immediately
4. **Twitch Live**: yt-dlp resolves the HLS stream → ffmpeg captures 30-second segments → plays on MFD with automatic segment cycling

## Supported Formats

- MP4 (H.264) - recommended
- WebM
- AVI
- MOV
- Any URL supported by yt-dlp (YouTube, Twitch, etc.)

## Configuration

Config file is generated at `BepInEx\config\com.noms.mfdvideoplayer.cfg` after first run.

| Setting | Default | Description |
|---------|---------|-------------|
| ToggleKey | F11 | Key to toggle video playback |
| Volume | 0.5 | Audio volume (0.0 - 1.0) |
| Loop | true | Loop video playback |
| YtDlpPath | (auto) | Path to yt-dlp.exe (auto-detects from plugins folder or PATH) |

## Changelog

### v2.0.0
- YouTube and Twitch URL streaming support via yt-dlp
- Twitch live stream support with ffmpeg segment capture and double-buffering
- Source selection UI (local files / stream URL)
- URL input dialog with Ctrl+V paste support
- Per-screen selection when multiple MFD screens are available
- Live stream HUD with segment counter
- Auto-detection of yt-dlp and ffmpeg from plugins folder, BepInEx root, game root, or PATH

### v1.0.0
- Local video file playback on MFD tactical screens
- Multi-file switching with Page Up/Down
- Volume control and loop toggle
- On-screen playback HUD

## Notes

- Aircraft without tactical screens (e.g., Chicane) are not supported
- Twitch live streams have ~30 second initial buffering time
- Twitch segments auto-cycle with pre-fetching to minimize gaps
- Netflix and other DRM-protected services are not supported
