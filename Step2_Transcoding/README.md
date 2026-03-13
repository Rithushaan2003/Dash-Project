# Step 2 — Video Transcoding (FFmpeg)

This step demonstrates the transcoding of two UHD video files into three different bitrates each, using FFmpeg.  
The purpose is to prepare the files for adaptive streaming, where multiple bitrate versions are required.

---

## 🎯 Task Overview

For each source video, I created three output versions at:

- 1.5 Mbps  
- 2.0 Mbps  
- 4.0 Mbps  

Screenshots of each transcoding process are included in this folder as evidence.

---

## 🛠️ FFmpeg Commands Used

### ▶️ Video 1 — 3127017-uhd_3840_2160_24fps.mp4

**1.5 Mbps**
ffmpeg -i 3127017-uhd_3840_2160_24fps.mp4 -b:v 1500k -bufsize 3000k 3127017_1500k.mp4

**2.0 Mbps**
ffmpeg -i 3127017-uhd_3840_2160_24fps.mp4 -b:v 2000k -bufsize 4000k 3127017_2000k.mp4

**4.0 Mbps**
ffmpeg -i 3127017-uhd_3840_2160_24fps.mp4 -b:v 4000k -bufsize 8000k 3127017_4000k.mp4

---

### ▶️ Video 2 — 5380054-uhd_3840_2160_30fps.mp4

**1.5 Mbps**
ffmpeg -i 5380054-uhd_3840_2160_30fps.mp4 -b:v 1500k -bufsize 3000k 5380054_1500k.mp4

**2.0 Mbps**
ffmpeg -i 5380054-uhd_3840_2160_30fps.mp4 -b:v 2000k -bufsize 4000k 5380054_2000k.mp4

**4.0 Mbps**
ffmpeg -i 5380054-uhd_3840_2160_30fps.mp4 -b:v 4000k -bufsize 8000k 5380054_4000k.mp4

---

## 📸 Evidence (Screenshots)

This folder contains six screenshots showing FFmpeg running during each transcoding:

- Video 1 — 1500k  
- Video 1 — 2000k  
- Video 1 — 4000k  
- Video 2 — 1500k  
- Video 2 — 2000k  
- Video 2 — 4000k  

(Filenames may vary depending on upload.)

---

## 📘 Explanation of Bitrate

Bitrate controls the amount of data used per second of video:

- Lower bitrate → smaller file size, lower quality  
- Higher bitrate → larger file size, higher quality  

Adaptive streaming uses multiple bitrates so the player can switch depending on network speed.

---

## ✔️ Step Completed

All six transcoded files were successfully generated and verified.
