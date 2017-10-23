# iOS-App-Store-Preview-Video-Upscale
Instructions to upscale iOS App Store Preview Video

## Create App Store Preview Video
Create App Store Preview video using iMovie or similar.

## Download & install FFMPEG
* Download FFMPEG http://www.ffmpegmac.net
* Extract
* Copy the ffmpeg files (3) to `/usr/local/bin`
* Make the ffmpeg files executable `sudo chmod +x /usr/local/bin/ff*`

## Upscale your App Preview video
From the Terminal 
`ffmpeg -i "input_video.mp4" -acodec copy -color_primaries 1 -color_trc 1 -colorspace 1 -crf 6 -vf scale=1080:1920,setsar=1:1 "output_video.mp4"`

`-color_primaries 1 -color_trc 1 -colorspace 1` helps keep the colours as close as possible.

`setsar=1:1` forces aspect ratio of 1:1, and hence maintains the resolution.

`-crf 6` sets desired quality (lower number is better quality).
