# Step 1 — Installing FFmpeg

This step involved installing the FFmpeg multimedia framework on the Linux server VM. FFmpeg is required for transcoding the HD videos into multiple bitrates for DASH streaming.

## Commands Used
sudo apt update
sudo apt install ffmpeg -y
ffmpeg -version

## Explanation
- `sudo apt update` refreshes the package list.
- `sudo apt install ffmpeg -y` installs FFmpeg and all required dependencies.
- `ffmpeg -version` verifies that the installation was successful.

## Evidence
Screenshots for this step are included in this folder.
