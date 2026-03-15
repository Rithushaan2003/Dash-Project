# Step 5 – DASH Client Test (Ubuntu Client VM)

## Overview
In this step, a second Linux virtual machine (Ubuntu Client) was created to test the DASH stream hosted on GitHub Pages. The purpose was to verify that the DASH manifest (`manifest.mpd`) can be accessed and played from an external client device.

## Process
1. Installed a new Ubuntu Client VM.
2. Opened Firefox inside the VM.
3. Navigated to the Bitmovin Test Player:
   https://bitmovin.com/demos/stream-test
4. Selected **DASH** as the stream type.
5. Entered the manifest URL hosted on GitHub Pages:
https://rithushaan2003.github.io/Dash-Project/Step4_DASH_Server/manifest.mpd (rithushaan2003.github.io in Google)
6. Clicked **Load Settings**, and the player successfully loaded and played the video.

## Evidence
Screenshots for this step are included in this folder.
- The Bitmovin player successfully playing the DASH stream.
- The Bitmovin configuration with the correct manifest URL entered.
