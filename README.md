# Custom-csm-gen; CSM Fork – Conversational Speech Modeling (Custom Setup)

This is a customized fork of [SesameAILabs/CSM](https://github.com/SesameAILabs/csm), designed for generating high-quality, speaker-conditioned speech using short reference audio samples and input text.

This fork has been tested and optimized for local deployment on high-memory GPUs (e.g., NVIDIA Quadro RTX 8000) with CUDA 12.2.

---

##  Overview

CSM (Conversational Speech Modeling) allows for:
- Multispeaker dialogue synthesis
- Natural, prompt-driven TTS generation
- Fast generation speeds on modern GPUs

This fork provides a clean and tested setup with:
- Enhanced logging
- Local hardware optimization
- A usage example for generating short conversations

---

##  System Requirements

This version has been verified on the following setup:

| Component         | Version / Detail               |
|------------------|--------------------------------|
| GPU              | NVIDIA Quadro RTX 8000 (48 GB) |
| CUDA             | 12.2                           |
| Driver           | 535.247.01                     |
| OS               | Ubuntu 20.04                   |
| Python           | 3.10 (Conda recommended)       |
| PyTorch          | 2.0+ with CUDA                 |

---

## 0 Installation

### 1. Clone the repository

###bash
git clone https://github.com/YOUR_USERNAME/csm-rtx8000-fork.git
cd csm-rtx8000-fork



pip install torch torchaudio huggingface_hub
conda create -n csm python=3.10 -y
conda activate csm
pip install torch torchaudio huggingface_hub

Using device: cuda
Generating: How are you?
Generating: ok, what about you?
Generating: I am fine too, thanks.
Generating: Good to know that! ?
Successfully generated full_conversation.wav


##Output

full_conversation.wav – The generated speech for the entire dialogue

Sample rate is 24kHz (default)

Each utterance is ~3–5 seconds depending on the input

##Customization

To modify the generated conversation, edit this block in run_csm.py:

conversation = [
    {"text": "How are you?", "speaker_id": 0},
    {"text": "ok, what about you?", "speaker_id": 1},
    {"text": "I am fine too, thanks.", "speaker_id": 0},
    {"text": "Good to know that! ?", "speaker_id": 1}
]

##Performance Notes

The model runs efficiently on GPUs with ≥24 GB VRAM

Peak usage on RTX 8000: ~2.5–3.5 GB

Generation takes ~1–2 seconds per utterance

Model uses float32 precision (no mixed precision yet)

📜 License

This project is licensed under the Apache 2.0 License, as per the original repo.

🙏 Acknowledgments

Thanks to Sesame AI Labs


📣 Citation

If you use this project in academic or research work, please cite the original authors:

Sesame AI Labs. “CSM: Conversational Speech Modeling.” https://github.com/SesameAILabs/csm
