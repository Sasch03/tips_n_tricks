# YouTube Music MP3 Exporter (Arch Linux Setup)

This guide contains optimized `yt-dlp` commands to download high-quality MP3s from YouTube Music. 

The configuration ensures full hardware compatibility with standalone MP3 players by embedding **PNG thumbnails** and writing **ID3v2.3 metadata tags**.

---

## Prerequisites

Ensure all required tools are installed on your Arch Linux system:

```bash
sudo pacman -S yt-dlp ffmpeg atomicparsley
```

---

## 1. Download Command (Without Cookies)

Use this standard command for public tracks and playlists where no age-restriction or account login is required.

```bash
yt-dlp -x --audio-format mp3 --audio-quality 0 --embed-thumbnail --convert-thumbnails png --embed-metadata --postprocessor-args "ffmpeg:-id3v2_version 3" -o "%(title)s.%(ext)s" "PASTE_URL_HERE"
```

---

## 2. Download Command (With Firefox Cookies)

Use this command for age-restricted content, private playlists, or restricted YouTube Music links. It uses your active Firefox session cookies.

> **Note:** If you get a `Database is locked` error, close Firefox before running the command.

```bash
yt-dlp --cookies-from-browser firefox -x --audio-format mp3 --audio-quality 0 --embed-thumbnail --convert-thumbnails png --embed-metadata --postprocessor-args "ffmpeg:-id3v2_version 3" -o "%(title)s.%(ext)s" "PASTE_URL_HERE"
```

---

## 3. Shell Aliases Configuration

To avoid typing long commands every time, add these shortcuts to your shell configuration file.

### Step 1: Open your shell config

For **Bash**:
```bash
nano ~/.bashrc
```

For **Zsh**:
```bash
nano ~/.zshrc
```

### Step 2: Add the aliases

Append the following lines to the bottom of the file:

```bash
# yt-dlp MP3 Exporter Shortcuts
alias yt-mp3='yt-dlp -x --audio-format mp3 --audio-quality 0 --embed-thumbnail --convert-thumbnails png --embed-metadata --postprocessor-args "ffmpeg:-id3v2_version 3" -o "%(title)s.%(ext)s"'

alias yt-mp3-cookie='yt-dlp --cookies-from-browser firefox -x --audio-format mp3 --audio-quality 0 --embed-thumbnail --convert-thumbnails png --embed-metadata --postprocessor-args "ffmpeg:-id3v2_version 3" -o "%(title)s.%(ext)s"'
```

### Step 3: Reload your shell

Save the file (`Ctrl+O`, `Enter`, then `Ctrl+X`) and reload the environment:

For **Bash**:
```bash
source ~/.bashrc
```

For **Zsh**:
```bash
source ~/.zshrc
```

---

## 4. Usage Example with Aliases

```bash
# Standard download:
yt-mp3 "https://music.youtube.com/watch?v=..."

# Download requiring Firefox cookies:
yt-mp3-cookie "https://music.youtube.com/watch?v=..."
```