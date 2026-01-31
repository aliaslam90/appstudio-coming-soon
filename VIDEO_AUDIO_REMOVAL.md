# Video Audio Removal

To ensure the hero background video has no audio track (required for mobile autoplay), use this ffmpeg command:

```bash
ffmpeg -i video/bg1.mp4 -an -c:v libx264 -pix_fmt yuv420p -movflags +faststart video/bg1-noaudio.mp4
```

**Command breakdown:**
- `-i video/bg1.mp4` - Input video file
- `-an` - Remove audio track
- `-c:v libx264` - Use H.264 video codec
- `-pix_fmt yuv420p` - Ensure compatibility
- `-movflags +faststart` - Optimize for web streaming
- `video/bg1-noaudio.mp4` - Output file

After creating the no-audio version, update `index.html` to use `video/bg1-noaudio.mp4` instead of `video/bg1.mp4`.
