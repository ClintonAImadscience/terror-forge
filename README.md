# TERROR FORGE  
**Extract clean training data from messy YouTube clips.**  
Built for red teamers, voice cloners, and audio freaks who need fast, accurate voice isolation.

---

##  What This App Does

Terror Forge takes in YouTube links where your target speaker appears — usually interviews, podcasts, or panels — and returns denoised, normalized, speaker-isolated `.wav` files that are ready for voice cloning model training.

It's optimized for **real-world red teaming**, where the only audio available might be a public-facing conversation with multiple people talking.

---

## WHat It Does Step-by-Step

1. **Downloads audio from YouTube** via `yt-dlp`  
2. **Converts to `.wav`** with consistent format (mono, same sample rate)  
3. **Slices out the middle X seconds** — you control how much  
4. **Trims silence** and **normalizes volume**  
5. **Runs speaker diarization** (with optional overlap removal) using `pyannote.audio`  
6. **Filters out crosstalk and short segments**  
7. **Exports speaker-separated chunks to your Google Drive**, using a custom label you define  

---

##  Built With

- `yt-dlp` for YouTube download  
- `ffmpeg` + `pydub` for audio slicing + normalization  
- `pyannote.audio` for speaker diarization + overlap detection  
- Google Colab for compute + Google Drive output  
- Structured logging throughout  

---

##  Why This Exists

Most open-source audio prep pipelines assume:  
- You have a single-speaker dataset already  
- You're working in a clean environment  

I don’t. I work in OSINT, AI red teaming, and real-world conditions where audio is chaotic and limited. Terror Forge is my response to that — something built to **actually get you clean speaker data** from messy clips, fast.

---

##  How To Use It

1. Open the script in Google Colab  
2. Add your Hugging Face token (for `pyannote`)  
3. Set:
   - `MIDDLE_SEGMENT_DURATION` to how many seconds you want  
   - `CUSTOM_LABEL` to tag your output files  
   - Your YouTube URLs  
4. Run Block 5 — it’ll do everything else
5. Oh wait you'll also need to set the paths for storing the data, to your Google Drive lol  

---

## Output

You’ll get `.wav` files like:/MyDrive/YouTubeAudio/Hook_Security_CEO_audio_0_SPEAKER_01_48000Hz.wav




---

##  License

This project is licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) License.  
Free to use commercially   Free to remix  
Just give me credit if you use it


---

## 🏴‍☠️ Author

Built by [@ClintonAImadscience](https://github.com/ClintonAImadscience), AI voice red teamer @ Breacher.ai  
I use this weekly to build voice clones from OSINT — now you can too.
