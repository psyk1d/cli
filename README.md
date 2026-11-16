# Video Template Agent

Turns a short video into a vertical (1080x1920) Reel/Short in a white "meme template" style:

- white area with a bold **hook/caption** on top
- your **video** in the middle (full width, never stretched or cropped)
- your **logo** (and optional handle) below the video

## Requirements

- Python 3.9+
- [ffmpeg](https://ffmpeg.org/download.html) installed and on your PATH
- `pip install -r requirements.txt`

## Web app (upload in the browser)

```
python3 app.py
```

Open http://localhost:5000, upload a video, type the hook, pick or upload a logo, and download the result.
Uploaded logos are saved in `logos/` so you can reuse them. Finished videos are saved in `outputs/`.

## Command line

```
python3 video_template_agent.py --video clip.mp4 --logo logo.png \
  --hook "Watching the trailer and you realize..." \
  --handle @mychannel --logo-pos center --out final.mp4
```

Options: `--logo-pos left|center|right`, `--logo-width 200`, `--font path/to/bold.ttf`.

If `--hook` is omitted and `ANTHROPIC_API_KEY` is set (with `pip install anthropic`), the CLI suggests
3 hooks based on frames from the video. Otherwise it asks you to type one.

## Notes

- Everything runs locally; videos are not uploaded anywhere.
- Only use footage you own or have rights to use.
