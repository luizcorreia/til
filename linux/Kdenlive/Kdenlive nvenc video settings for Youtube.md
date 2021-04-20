
# Kdenlive nvenc video settings for Youtube

After numerous tryings in to follow codec settings for youtube in order to processing time after the video was uploaded, I've come up with the following Kdenlive settings for 1080p video using Nvidia hardware.

```bash
f=mp4 vcodec=nvenc_h264 acodec=aac ab=384k g=15 profile:v=high global_quality=21 -coder 1 vq=21 -r 29.97 preset=slow bf=2 movflags=faststart pix_fmt=yuv420p
```

The thing these settings don't have is bitrate limit, however in the videos I've encoded, I didn't notice exceeding bitrate it always seem to be under 15Mbps.

Here's my rationale for each of these encoding options.

- **f=mp4** use mp4 container
- **vcodec=nvenc_h264** utilize nvidia hardware acceleration
- **acodec=aac ab=384k** use AAC audio codec with bitrate 384k
- **global_quality=21 -coder 1 vq=21 preset=slow** following some of the recommendations from this stackoverflow answer on intricacies of nvidia encoder
- **-r 29.97** use 29.97 FPS frame rate. This is the framerate I shoot the video with and this is the framerate I use to publish video. This will avoid recording light flickering effect in North America power grid.
- **bf=2** 2 consecutive B-frames (youtube recommendation)
- **movflags=faststart** youtube recoomendation (mp4 container), see additional discussion on superuser.com
- **pix_fmt=yuv420p** pixel format/color encoding to use (youtube recommendation)

### References:

[Recommended upload encoding settings](https://support.google.com/youtube/answer/1722171?hl=en)

[Best settings for FFMpeg with NVENC](https://superuser.com/a/1296511/420376)

[Any downsides to always using the -movflags faststart parameter?](https://superuser.com/questions/856025/any-downsides-to-always-using-the-movflags-faststart-parameter)