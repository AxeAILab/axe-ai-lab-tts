<p align="center">
  <img src="https://img.shields.io/badge/Axe%20AI%20Lab-TTS%20Studio-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/GPU-T4-76b900?style=for-the-badge&logo=nvidia&logoColor=white" />
  <img src="https://img.shields.io/badge/Model-Kokoro--82M-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Tunnel-Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/License-Apache%202.0-green?style=for-the-badge" />
</p>

<h1 align="center">🪓 Axe AI Lab — TTS Studio</h1>
<p align="center">
  <b>Free, GPU-accelerated Text-to-Speech on Google Colab</b><br/>
  Powered by Kokoro-82M · 10 Languages · 20+ Voices · Cloudflare Public URL
</p>

---

## ✨ Features

- 🚀 **Runs free on Google Colab T4 GPU** — no paid API keys needed
- 🗣️ **Kokoro-82M model** — 82M parameter TTS, Apache 2.0 licensed, 24kHz output
- 🌍 **10 languages** — English (US/UK), Hindi, Japanese, Chinese, Spanish, French, Italian, Portuguese, Korean
- 🎙️ **20+ distinct voices** — multiple male and female options per language
- 🔗 **Cloudflare Quick Tunnel** — instant public URL, share with anyone
- 🎛️ **Full Gradio UI** — speed control, voice picker, generation history, examples
- 🐍 **Python 3.12 compatible** — works with the latest Colab runtime

## 🖥️ Screenshot

```
🪓 AXE AI LAB
TTS Studio · Kokoro-82M · GPU Accelerated

┌─────────────────────────────┬──────────────────────┐
│  Text to Synthesize         │  Output Audio        │
│  ┌─────────────────────┐    │  ▶ ████████░░ 0:04  │
│  │ Type your text...   │    │                      │
│  └─────────────────────┘    │  Status              │
│                             │  ✅ Done in 1.2s     │
│  Language    Voice          │  English | af_heart  │
│  [English▼] [af_heart▼]    │                      │
│                             │  GPU Memory          │
│  Speed  ──●──────  1.0x    │  VRAM: 1.2/15.0 GB  │
│                             │                      │
│  [  GENERATE SPEECH  ]      │                      │
└─────────────────────────────┴──────────────────────┘
```

## 🚀 Quick Start

### Option 1 — Open in Colab (recommended)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AxeAILab/axe-ai-lab-tts/blob/main/Axe_AI_Lab_TTS_Studio.ipynb)

### Option 2 — Clone and open manually

```bash
git clone https://github.com/YOUR_USERNAME/axe-ai-lab-tts.git
```

Then upload `Axe_AI_Lab_TTS_Studio.ipynb` to [colab.research.google.com](https://colab.research.google.com).

## 📋 Run Order

> ⚠️ First: `Runtime → Change runtime type → T4 GPU → Save`

| # | Cell | Description | Est. Time |
|---|------|-------------|-----------|
| 1 | GPU Check | Confirms T4 is active, shows VRAM | ~5s |
| 2 | Install | Kokoro, Gradio, espeak-ng, ffmpeg, cloudflared | ~2 min |
| 3 | Load Model | Downloads Kokoro-82M (~330MB, cached after) | ~60s |
| 4 | Launch UI | Starts Gradio on port 7860 | ~10s |
| 5 | Tunnel | Cloudflare Quick Tunnel → public URL | ~10s |

After Cell 5, you'll see:

```
══════════════════════════════════════════════════════════
  🪓  AXE AI LAB — TTS STUDIO
══════════════════════════════════════════════════════════
  PUBLIC URL : https://xxxx-yyyy-zzzz.trycloudflare.com
══════════════════════════════════════════════════════════
  Share this link — opens from any device!
══════════════════════════════════════════════════════════
```

## 🎙️ Voices

| Language | Voices |
|----------|--------|
| 🇺🇸 English (US) | `af_heart` `af_bella` `af_sarah` `am_adam` `am_michael` |
| 🇬🇧 English (UK) | `bf_emma` `bf_isabella` `bm_george` `bm_lewis` |
| 🇮🇳 Hindi | `hf_alpha` `hf_beta` `hm_omega` |
| 🇯🇵 Japanese | `jf_alpha` `jf_gongitsune` `jm_kumo` |
| 🇨🇳 Chinese | `zf_xiaobei` `zf_xiaoni` `zm_yunjian` |
| 🇪🇸 Spanish | `ef_dora` `em_alex` `em_santa` |
| 🇫🇷 French | `ff_siwis` |
| 🇮🇹 Italian | `if_sara` `im_nicola` |
| 🇧🇷 Portuguese | `pf_dora` `pm_alex` `pm_santa` |
| 🇰🇷 Korean | `kf_alpha` `km_omega` |

**Tips:**
- `af_heart` — warm, natural, great for general use
- `bm_george` — authoritative British male
- Speed `0.9` often sounds the most natural
- Punctuation significantly improves prosody

## 🏗️ Tech Stack

| Component | Technology |
|-----------|-----------|
| TTS Model | [Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) |
| UI Framework | [Gradio](https://gradio.app) |
| GPU Runtime | Google Colab T4 |
| Public Tunnel | [Cloudflare Quick Tunnels](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/do-more-with-tunnels/trycloudflare/) |
| Phonemizer | espeak-ng |

## 📁 Repo Structure

```
axe-ai-lab-tts/
├── Axe_AI_Lab_TTS_Studio.ipynb   # Main Colab notebook
├── requirements.txt               # Python dependencies (reference)
├── LICENSE                        # Apache 2.0
└── README.md                      # This file
```

## 📦 Dependencies

```
kokoro>=0.9.4
gradio>=4.44.0
soundfile
scipy
pydub
numpy
```

System packages: `espeak-ng`, `ffmpeg`

## ❓ FAQ

**Q: Do I need a GPU?**  
A: Strongly recommended. CPU works but is very slow (~30s per sentence). Select T4 in Colab runtime settings — it's free.

**Q: Does the public URL expire?**  
A: Yes — Cloudflare Quick Tunnel URLs are valid for the duration of your Colab session only. Run Cell 5 again after a disconnect to get a new URL.

**Q: Can I clone voices?**  
A: Kokoro-82M is a multi-speaker model with fixed voices. For voice cloning, we'll add a XTTS-v2 branch once Coqui resolves Python 3.12 compatibility.

**Q: How long can the text be?**  
A: No hard limit. Kokoro processes text in chunks automatically. Long articles work fine; just expect proportionally longer generation time.

**Q: Is this free to use commercially?**  
A: Kokoro-82M is Apache 2.0 licensed — yes, commercial use is allowed.

## 🤝 Contributing

PRs welcome! Ideas:

- [ ] Batch mode (multiple texts → zip of audio files)
- [ ] SSML markup support
- [ ] Audio post-processing (normalize, trim silence)
- [ ] More language pipelines as Kokoro adds them
- [ ] Docker container version

## 📄 License

This project is licensed under the **Apache 2.0 License** — see [LICENSE](LICENSE) for details.  
Kokoro-82M model is also Apache 2.0. See [hexgrad/Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) for model license details.

---

<p align="center">
  Built with ❤️ by <b>Axe AI Lab</b>
</p>
