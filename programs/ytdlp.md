# yt-dlp

**yt-dlp** adalah alat atau program yang dibuat berdasarkan *youtube-dl* dengan
menambahkan beberapa fungsionalitas dan perbaikan.

Untuk informasi lebih lengkap terkait konfigurasi *yt-dlp* dapat langsung
mengakses github berikut: [https://github.com/yt-dlp/yt-dlp](https://github.com/yt-dlp/yt-dlp)

## Instalasi

**Archlinux:**

```bash
sudo pacman -S yt-dlp ffmpeg atomicparsley python-mutagen python-pycryptodome \
python-websockets python-brotli python-xattr python-secretstorage
```

## Konfigurasi

Konfigurasi ini disesuaikan dengan keinginan masing-masing.
Secara personal berikut adalah konfigurasi saya.

### Audio

Untuk mendownload audio, saya menggunakan config khusus audio yaitu `audioconfig`
yang terletak di `~/.config/yt-dlp/audioconfig`

```bash
--extract-audio
--audio-quality 0
--audio-format mp3
--no-mtime
-o '$HOME/downloads/music/%(title)s.%(ext)s'
```

Dengan file config khusus ini, saya membuat alias berikut untuk
untuk mempermudah dalam penggunaannya.

```bash
alias ytaudio='yt-dlp --config-location ~/.config/yt-dlp/audioconfig'
```
