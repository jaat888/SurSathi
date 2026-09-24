# 🎵 SurSathi

> **A modern Flutter music player built for listeners who love Hindi, Haryanvi and Punjabi music.**

SurSathi is an Android music player focused on a smooth listening experience, powerful personal library tools, background playback and a clean, customizable interface.

The project is built with **Flutter + Dart**, with a native Android/Kotlin layer for parts of the audio/source integration.

---

## ✨ What makes SurSathi different?

SurSathi is designed around a simple idea: **your music, your library, your way of listening.**

Instead of keeping the experience limited to a basic search-and-play screen, the app brings together discovery, playlists, radio-style listening, local caching, downloads, lyrics, personalization and playback controls in one place.

---

## 🚀 Features

### 🎧 Music Playback

- Smooth audio playback with `just_audio`
- Background playback
- Play / pause / next / previous / seek
- Shuffle and repeat modes
- Queue management with reorder support
- Media controls for headphones and Bluetooth devices
- Audio focus and interruption handling
- Sleep timer
- Automatic retry/fallback handling around stream resolution

### 🔎 Search & Discovery

- Music search
- Recent searches
- Popular search suggestions
- Artist pages
- Album pages
- Curated playlists
- Mood-based music sections
- Daily Mix style playlists
- Smart playlist views
- Similar-artist discovery
- Multiple source/service integrations used by the app for discovery and matching

### 📻 Radio Mode

SurSathi includes a dedicated radio-style listening experience with:

- Continuous track discovery
- Upcoming-track candidates
- Played-track history
- Language-aware filtering
- Candidate filtering and matching
- Local playback/cache reuse where available
- Playback transition protection to reduce rapid command races
- Radio lyrics support

### 📝 Lyrics

- Lyrics screen integrated into the player
- Lyrics caching
- Cached lookup to reduce repeated requests
- Radio-focused lyrics handling
- Full-screen lyrics view

### 📚 Personal Library

- Liked Songs
- Downloads
- Playlists
- Playlist creation and editing
- Playlist descriptions
- Private playlist option
- Playlist cover customization
- Add/remove songs from playlists
- Reorder playlist tracks
- Play All and Shuffle

### 💾 Downloads & Local Playback

- Download queue
- Download management screen
- Local playback of downloaded tracks
- Download database tracking
- Persistent local storage helpers
- Cached media indicator

### ⚡ Smart Cache

SurSathi maintains a local playback cache to reduce unnecessary repeated network work.

- Configurable cache size
- LRU-style cleanup of unprotected items
- Protected/liked content handling
- Wi-Fi-only cache option
- Preload-next-song option
- Cache manager screen
- Clear-all and clear-unprotected actions

### 🎨 UI & Personalization

- Dark, music-focused interface
- Sora + Inter typography
- Multiple accent color options
- Font-size controls
- Animation-speed controls
- Dynamic color support
- Animated mini player
- Full-screen vinyl-style player
- Responsive player controls
- Shimmer loading states
- Haptic feedback on selected actions

### 🎚️ Audio & Player Tools

- 10-band equalizer interface
- Presets
- Bass boost controls
- 3D surround / reverb controls in the player UI
- Queue screen
- Sleep timer
- Background playback settings
- Audio-session handling

### ☁️ Backup & Device Tools

- Backup / restore tools
- Silent backup support
- Device-to-web connection flow
- Playlist/library transfer support
- Import playlist support
- Duplicate-song cleanup screen

### 📊 Library Statistics

- Listening statistics screen
- Week / Month / Year / All range views
- Library counters for likes, playlists and downloads
- Profile-style listening overview

### 🔄 Updates

- Built-in “Check for Update” flow
- Downloaded APK installation flow
- Force-update screen support

---

## 🧩 Technology Stack

| Layer | Technology |
|---|---|
| UI | Flutter / Dart |
| State management | Provider |
| Audio playback | just_audio |
| Background audio | audio_service |
| Audio session | audio_session |
| Local database | SQLite / sqflite |
| Preferences | SharedPreferences |
| Networking | HTTP / WebSocket |
| Images & caching | cached_network_image / flutter_cache_manager |
| Native Android | Kotlin |
| YouTube extraction layer | NewPipeExtractor (native Android integration) |
| Typography | Google Fonts |

---

## 🏗️ Project Structure

```text
SurSathi/
├── android/              # Android + native Kotlin layer
├── assets/               # App assets and audio
├── lib/
│   ├── db/               # SQLite databases
│   ├── models/           # Song / Playlist models
│   ├── screens/          # App screens
│   ├── services/         # Playback, radio, cache, lyrics, etc.
│   ├── theme/            # Colors, theme and typography
│   └── widgets/          # Reusable UI components
├── test/                 # Automated tests
├── build_release.sh      # Release build helper
├── pubspec.yaml          # Flutter dependencies
└── LICENSE               # Project license
```

---

## 📱 Main Screens

SurSathi currently includes a broad set of screens/modules, including:

**Home · Search · Library · Downloads · Full Player · Queue · Lyrics · Radio · Playlists · Artist · Album · Daily Mix · Smart Playlists · Stats · Equalizer · Cache Manager · Settings · Theme Customizer · Backup/Restore · Connect to Web · Profile · Help · About**

---

## 🎯 Design Philosophy

SurSathi aims to keep the important controls close to the listener while avoiding a cluttered interface.

The player is built around:

- fast access to playback controls
- clear queue management
- persistent library data
- reusable local cache
- background listening
- responsive animations and feedback
- customizable visual preferences

---

## 🛠️ Requirements

To build the project locally, you will need:

- Flutter SDK compatible with the project's SDK constraints
- Android SDK / Android Studio tooling
- JDK compatible with the configured Android Gradle setup
- A connected Android device or emulator

The Android module currently uses **compileSdk 36** and **minSdk 23**.

---

## ▶️ Run the App

```bash
flutter pub get
flutter analyze
flutter test
flutter run
```

For a normal release APK:

```bash
flutter build apk --release
```

For the project's release helper:

```bash
bash build_release.sh
```

The release helper builds the APK with Dart obfuscation and stores the corresponding debug symbol files separately.

> **Important:** Keep obfuscation symbol files private. They are useful for decoding obfuscated crash stack traces and should not be committed to a public repository.

---

## 🧪 Testing

The repository contains tests covering areas such as:

- local media resolution
- radio engine behaviour
- queue/shuffle behaviour
- JioSaavn parsing
- mood catalog handling
- radio candidate filtering
- radio history concurrency
- lyrics quality
- curated-match caching

Run all tests with:

```bash
flutter test
```

---

## 🔐 Privacy & Security Notes

SurSathi requests Android permissions required for features such as networking, notifications, background playback, media access, voice search and update installation.

The app should only be granted permissions necessary for the features a user chooses to use.

Do not commit private keys, signing credentials, API secrets or release symbol files to GitHub.

Use the provided example configuration files where applicable instead of committing real secrets.

---

## ⚖️ Content & Source Disclaimer

SurSathi is a music-player application. It does not claim ownership of third-party music, artwork, lyrics or other media made available by external services.

Content availability can depend on the source service, region, network conditions and the terms/policies applicable to that service.

Users are responsible for using the application and accessing content in accordance with applicable laws and the terms of the relevant services.

---

## 📦 License

SurSathi is released under the **GNU General Public License v3.0 or later (GPL-3.0-or-later)**.

See the [`LICENSE`](LICENSE) file for the full license text.

This repository also contains third-party dependencies. Their respective licenses and notices continue to apply to those components.

---

## 🙌 Credits

SurSathi is built with the help of the open-source Flutter/Dart ecosystem and other open-source libraries used by the project.

Special thanks to the maintainers and contributors of the libraries that make modern mobile audio, storage, networking and UI development possible.

---

## 🌱 Project Status

SurSathi is an actively developed project. Features and internals may continue to change as playback reliability, radio behaviour, UI polish and source integrations evolve.

The public repository should be treated as the project's source of truth for the code and current implementation.

---

## ⭐ Support the Project

If you find SurSathi interesting, you can:

- ⭐ Star the repository
- 🐛 Report reproducible bugs
- 💡 Open feature requests
- 🔧 Submit improvements and fixes

Please include clear reproduction steps when reporting playback, radio or source-resolution issues.

---

<p align="center">
  <b>SurSathi — Apni Music, Apne Andaaz Mein. 🎵</b>
</p>
