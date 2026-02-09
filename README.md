# Nuclear Option - MFD Video Player

Play custom videos on your cockpit MFD screens. Drop video files into the plugin folder and watch them in-flight on your tactical displays.

![BepInEx](https://img.shields.io/badge/BepInEx-5.x-blue) ![Game](https://img.shields.io/badge/Nuclear%20Option-Steam-black)

## Requirements

- [Nuclear Option](https://store.steampowered.com/app/2296550/Nuclear_Option/) on Steam
- [BepInEx 5.x](https://github.com/BepInEx/BepInEx/releases) (Unity Mono)

## Installation

1. Install BepInEx 5.x into your Nuclear Option game folder
2. Run the game once to generate the BepInEx folder structure
3. Copy `MFDVideoPlayer.dll` into `[Game Folder]\BepInEx\plugins\`
4. Place your video files (`.mp4`, `.webm`, `.avi`, `.mov`) in the same `plugins` folder
5. Launch the game

## Controls

| Key | Function |
|-----|----------|
| `F11` | Toggle video playback on/off |
| `Page Up` | Next video |
| `Page Down` | Previous video |
| `+` | Volume up |
| `-` | Volume down |

## Features

- Plays video files on all cockpit MFD/tactical screens
- Supports multiple video files with switching
- Adjustable volume
- Loop playback (configurable)
- On-screen HUD showing current file, time, and controls
- HUD information remains visible while screens show video

## Supported Formats

- MP4 (H.264) - recommended
- WebM
- AVI
- MOV

## Configuration

Config file is generated at `BepInEx\config\com.yuulf.mfdvideoplayer.cfg` after first run.

| Setting | Default | Description |
|---------|---------|-------------|
| ToggleKey | F11 | Key to toggle video playback |
| Volume | 0.5 | Audio volume (0.0 - 1.0) |
| Loop | true | Loop video playback |

## Notes

- Video plays on all tactical screens simultaneously
- The HUD overlay still displays all essential flight/combat information
- Aircraft without tactical screens (e.g., Chicane) are not supported
- Stopping playback restores the original radar display
