# 🎥 OBS Live Setup Guide

This guide provides recommended settings for configuring **OBS Studio** (Open Broadcaster Software) to get the best video and audio quality for live streaming — whether you're gaming, teaching, or broadcasting events.

---

## 🔧 Video Output Settings

Navigate to **Settings → Video** in OBS.

| Setting                     | Recommended Value         | Notes                                                        |
|----------------------------|---------------------------|--------------------------------------------------------------|
| **Base (Canvas) Resolution**  | `1920x1080`                 | The resolution of your monitor or source.                    |
| **Output (Scaled) Resolution** | `1280x720` *(or `1920x1080`)* | Final stream resolution. Lower it for better performance.    |
| **Downscale Filter**       | `Lanczos (36 samples)`     | Best quality. Use `Bicubic` for performance.                 |
| **FPS (Frames Per Second)** | `30` or `60`               | 60fps for smooth video (games), 30fps for presentations.     |

---

## ⚙️ Output Settings (Streaming)

Go to **Settings → Output → Streaming**.

### Encoder Settings

| Setting            | Value                     | Notes                                                     |
|--------------------|---------------------------|-----------------------------------------------------------|
| **Encoder**         | Hardware (e.g., NVENC/AMD/Apple VT) | Use GPU-based encoding if available.                      |
| **Rate Control**    | `CBR`                     | Required for most platforms.                             |
| **Bitrate**         | `2500–4000 kbps` for 720p<br>`4500–6000 kbps` for 1080p | Choose based on your internet upload speed.             |
| **Keyframe Interval** | `2`                     | Required by platforms like Twitch and YouTube.            |
| **Preset** (NVENC)  | `Quality` or `Max Quality` | Balance between quality and performance.                  |
| **Profile**         | `High`                    | Ensures compatibility and stability.                      |
| **Look-Ahead**      | `Enabled` *(optional)*     | Dynamically adjusts bitrate during motion.                |
| **Psycho Visual Tuning** | `Enabled`              | Improves visual fidelity during movement.                 |
| **GPU**             | `0`                        | Default. Only change if using multiple GPUs.              |
| **Max B-frames**    | `2`                        | Standard setting.                                         |

---

## 🔊 Audio Output Settings

Navigate to **Settings → Audio**.

| Setting         | Value     | Notes                                                  |
|-----------------|-----------|--------------------------------------------------------|
| **Sample Rate** | `48 kHz`  | Standard for high-quality streaming.                  |
| **Channels**    | `Stereo`  | Best compatibility across platforms.                  |
| **Desktop Audio** | Your main audio output device | Captures in-game or system sound.               |
| **Mic/Aux Audio** | Your microphone input         | Preferably an external mic for clear voice.      |

---

### Audio Bitrate Settings

Go to **Settings → Output → Audio**.

| Track             | Bitrate (kbps) |
|------------------|----------------|
| Streaming Track  | `160`          |
| Music/Voice Track| `192–256`      |
| Max Quality Audio| `320`          |

---

## 🚀 Tips for Best Performance

- ✅ Use **hardware encoder** if available (like NVENC or AMD).
- ✅ Monitor **CPU usage**, **dropped frames**, and **bitrate stability**.
- ✅ **Test your stream** using private or unlisted mode before going live.
- ✅ Choose a **nearby ingest server** on your streaming platform.
- ✅ Keep OBS and GPU drivers **up to date**.

---

## 💡 Personalized Help

To get optimized settings for your setup, consider:

- Your **CPU, GPU, and RAM specs**
- Your **internet upload speed**
- Your **streaming platform** (Twitch, YouTube, Facebook, etc.)

Let us know these, and we’ll help you tune your OBS configuration further.

---

# 📶 OBS Bitrate Recommendations

This guide provides bitrate recommendations for OBS Studio based on video resolution, frame rate, and streaming platform. Bitrate directly impacts stream quality and performance — so choosing the right one is crucial.

---

## 🖥 Video Bitrate by Resolution & Frame Rate

| Resolution     | Frame Rate | Recommended Bitrate (CBR) | Internet Upload Speed Required |
|----------------|------------|----------------------------|-------------------------------|
| 480p (SD)      | 30 fps     | 800 – 1,200 kbps           | ≥ 2 Mbps                      |
| 720p (HD)      | 30 fps     | 2,500 – 4,000 kbps         | ≥ 5 Mbps                      |
| 720p (HD)      | 60 fps     | 3,500 – 5,000 kbps         | ≥ 6 Mbps                      |
| 1080p (Full HD)| 30 fps     | 4,000 – 5,000 kbps         | ≥ 6 Mbps                      |
| 1080p (Full HD)| 60 fps     | 5,000 – 7,000 kbps         | ≥ 8 Mbps                      |
| 1440p (2K)     | 60 fps     | 9,000 – 13,000 kbps        | ≥ 16 Mbps                     |
| 4K (2160p)     | 60 fps     | 13,000 – 20,000+ kbps      | ≥ 25 Mbps                     |

> ⚠️ Choose no more than **70–80% of your upload bandwidth** to avoid buffering.

---

## 🎙 Audio Bitrate Recommendations

| Audio Track     | Bitrate     |
|-----------------|-------------|
| Voice Only      | 96 – 160 kbps |
| Voice + Background Music | 192 – 256 kbps |
| High-Quality Audio | 320 kbps (maximum) |

- Use **48 kHz** sample rate and **Stereo** channels for best results.

---

## 🌐 Platform-Specific Bitrate Limits

| Platform       | Max Video Bitrate | Notes                                       |
|----------------|--------------------|---------------------------------------------|
| **YouTube Live**  | 51,000 kbps (for 4K 60fps) | Scales with resolution. Supports HDR.        |
| **Twitch**        | ~6,000 kbps (unofficial cap) | For 1080p60. Higher bitrates may get throttled. |
| **Facebook Live** | 4,000 kbps + 128 kbps audio | Strict limits. 720p60 recommended.           |
| **Zoom/Meet**     | ~1,500–3,000 kbps            | Auto-adjusts, not manual.                    |
| **Custom RTMP**   | Depends on server            | Use your own server settings.                |

---

## 📌 Notes

- Use **CBR (Constant Bitrate)** for streaming; VBR (Variable) is better for local recording.
- If you're dropping frames, lower your resolution or bitrate.
- Use OBS hardware encoders (like NVENC or Apple VT) for better performance.

---

## 🧠 Quick Test Formula

**Upload speed × 0.75 = Safe max video bitrate**

> Example: `10 Mbps × 0.75 = 7,500 kbps max bitrate`

---
