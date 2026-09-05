# FineTune
*It will free you from hassle while fine tuning ai model.*

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/boss-defender/FineTune/blob/main/SmartFineTuner.ipynb)


**🎯 Check Github Repo here:**

**📍 https://github.com/boss-defender/Smart-Fine-Tune**

**⚡ Powered by [unslothai/unsloth](https://github.com/unslothai/unsloth).**

# ⚡ Unsloth Auto-Trainer: Interruption-Proof LLM Fine-Tuning Pipeline

**Run-and-forget fine-tuning for Google Colab.** Automatically handles GPU disconnections, saves training state directly to Google Drive with SHA-256 experiment isolation, and exports clean 16-bit merged base weights ready for local GGUF conversion or Hugging Face uploads! 🚀

---

# 🤔 Beginner ? Don't worry .

**🌐 Just give Model path and Dataset path from hugging face or Google Drive.**

**⚙️ Set max sample minimum 1000. But no input in max sample will lead this code to use whole dataset.**

**💡 Keep other box empty as it is.**

**🛠️ If you have technical knowledge , fill up those box carefully**

**✨ Click run & see the magic.**

---

## 🌟 Why Use This Pipeline?

Fine-tuning LLMs on Google Colab free or T4 runtimes often leads to lost progress from quota limits, session timeouts, and random disconnections. This pipeline solves every single headache:

* 🛡️ **Zero Headaches & Auto-Resume**: Automatically saves checkpoints to your Google Drive every N steps. If Colab disconnects, hit **Run All** again—it picks up at the exact step where it stopped!
* 🔒 **SHA-256 Experiment Isolation**: Every unique combination of model, dataset, learning rate, and batch size generates a cryptographically unique folder ID. Changing a hyperparameter automatically routes to a fresh workspace—zero risk of overwriting old runs!
* 📜 **`run_config.json` Safety Lock**: Reads saved parameter signatures before resuming to guarantee your hyperparameters match 100%.
* ⚡ **Unsloth Powered Speed**: Uses Unsloth's ultra-optimized 4-bit LoRA training for maximum VRAM efficiency and blazing speed.
* 📦 **Modular 16-Bit Merged Base Export**: Automatically exports a standalone 16-bit merged base model on completion so you can easily run GGUF quantization locally on your own PC.

---

## 📁 Google Drive Auto-Saving Architecture

Your checkpoints are stored safely inside your Google Drive using dynamic fingerprinting:

```text
Google Drive/
└── unsloth_checkpoints/
    ├── Llama_3_2_3B_Instruct__dolly_15k_oai_style__a1b2c3d4/
    │   ├── run_config.json          <-- Verifies exact parameters before resuming
    │   ├── checkpoint-25/
    │   ├── checkpoint-50/
    │   └── ...
    └── Qwen2_5_7B_Instruct__FineTome_100k__f9e8d7c6/
