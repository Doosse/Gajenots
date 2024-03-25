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

Cara penggunaan:

```bash
ytaudio *link youtube*
```

### Video

 Untuk konfigurasi video, saya juga menggunakan config spesifik
 sesuai dengan service yang didukung:
 [https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)

#### Youtube

Untuk *youtube*, saya menggunakan config yaitu `ytconfig` yang terletak
di `~/.config/yt-dlp/ytconfig`

```bash
--embed-thumbnail
--merge-output-format mp4
-f 'bv*+ba'
-o '$HOME/downloads/yt_%(id)s.%(ext)s'
```

dengan file config khusus ini, saya menggunakan alias berikut untuk
mempermudah dalam penggunaannya.

```bash
alias ytvideo='yt-dlp --config-location ~/.config/yt-dlp/ytconfig'
```

File config ini akan mendownload versi terbaik dari format yang tersedia.
Jika ingin mendownload format lain, sesuaikan dengan keinginan.

Cara penggunaan:

```bash
ytvideo *link youtube*
```

#### Vidio

Untuk *vidio*, saya menggunakan config yaitu `vidconfig` yang terletak
di `~/.config/yt-dlp/vidconfig`

```bash
--output "$HOME/downloads/video/vidio_%(title)s.%(ext)s"
--check-formats
--sub-format best
--sub-langs id
--embed-thumbnail
--embed-subs

```

dengan file config khusus ini, saya menggunakan alias berikut untuk
mempermudah dalam penggunaannya.

```bash
alias downvidio='yt-dlp --config-location ~/.config/yt-dlp/vidconfig'
```

File config ini akan mendownload versi terbaik dari format yang tersedia kemudian
mendownload thumbnail dan subtitle lalu menggabungkannya menjadi satu file `.mp4`.
Jika ingin mendownload format lain, sesuaikan dengan keinginan.

Cara penggunaan:

```bash
downvidio *link vidio*
```
