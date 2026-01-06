# ResourceAI

<div align="center">
  <img src="public/brand/logo.png" alt="ResourceAI Logo" width="120" height="120" />
  <h1>Your Private AI. Running Locally.</h1>
  
  <p>
    <strong>Zero cloud dependencies. 100% Offline.</strong><br>
    The power of Large Language Models (LLMs), optimized for your personal hardware.
  </p>

  <p>
    <a href="https://resourceai.fenixresource.com"><strong>Website & Download</strong></a> · 
    <a href="https://github.com/ResourceAI-app/resourceai/issues">Report Bug</a>
  </p>

  <br>

  ![macOS](https://img.shields.io/badge/macOS-Apple%20Silicon-000000?style=flat-square&logo=apple)
  ![Windows](https://img.shields.io/badge/Windows-Vulkan-0078D6?style=flat-square&logo=windows)
  ![Privacy](https://img.shields.io/badge/Privacy-Local%20SQLite-4CAF50?style=flat-square&logo=sqlite)
</div>

<br>

## 🚀 Overview

**ResourceAI** is a native desktop application designed to run GGUF-quantized Large Language Models (LLMs) directly on your computer. 

Unlike web-based AI services, ResourceAI runs **locally**. Your prompts, documents, and chat history never leave your device. We combine a high-performance **Rust** backend with a beautiful **Flutter** frontend to deliver a smooth, native experience on macOS and Windows.

## 🎥 See it in Action

[![ResourceAI Demo](https://resourceai.fenixresource.com/docs/1-overview.png)](https://resourceai.fenixresource.com/videos/test-llm.mov)

> *Click the image above to watch the demo video.*

## ✨ Key Features

- **🔒 Absolute Privacy:** All inference happens in RAM. Chat history is stored in a local encrypted SQLite database.
- **✈️ Fully Offline:** Works without an internet connection (once models are downloaded).
- **⚡ Hardware Accelerated:**
  - **macOS:** Native **Metal** support for Apple Silicon (M1/M2/M3).
  - **Windows:** Broad **Vulkan** support for NVIDIA, AMD, and Intel GPUs.
- **📦 Model Manager:** Integrated downloader for GGUF models from HuggingFace.
- **🧠 Context Aware:** Full control over system prompts and model parameters.

---

## 🛠️ Architecture & Compatibility

We engineered ResourceAI to be accessible to everyone, not just those with expensive enterprise GPUs.

### macOS (Apple Silicon)
On macOS, we leverage the **Metal Performance Shaders (MPS)** pipeline.
- **Optimization:** Unified Memory Architecture (RAM = VRAM).
- **Performance:** On M2/M3 chips, token generation is incredibly fast (40-60 t/s on 7B models).
- **Requirement:** macOS 12 (Monterey) or later.

### Windows (Vulkan)
Instead of relying solely on CUDA (which restricts usage to NVIDIA cards), ResourceAI uses **Vulkan** as the primary backend for Windows.

**Why Vulkan?**
- ✅ **Universal Support:** Runs on NVIDIA GeForce, AMD Radeon, and even **Intel Integrated Graphics (Iris Xe/UHD)**.
- ✅ **Stability:** Provides a consistent API across different hardware vendors.
- ✅ **Future Proof:** As NPU/iGPU hardware improves, Vulkan drivers update automatically.

> **Note for NVIDIA Users:** While we support NVIDIA cards via Vulkan, we are working on an optional CUDA backend for future releases to squeeze out maximum peak performance. For now, Vulkan ensures that *everyone* can run the app.

---

## 📥 Installation

### macOS
1. Download the latest `.dmg` from our [Website](https://resourceai.fenixresource.com).
2. Open the disk image and drag **ResourceAI** to your **Applications** folder.
3. Launch the app.
   - *Requirement:* macOS 12.0+ (Apple Silicon recommended).

### Windows
1. Download the `.exe` installer.
2. Run the installer (Accept the SmartScreen warning if it appears; we are currently in the process of certifying our code signing).
3. Ensure your **GPU Drivers** are up to date (Vulkan libraries are usually included with standard driver updates).

---

## 🏎️ Performance Benchmarks

Real-world performance observed on common consumer hardware:

| Hardware | Model Size | Speed (approx.) | Usage |
|----------|------------|-----------------|-------|
| **MacBook Air M2** (16GB) | 7B (Q4_K_M) | ~25 t/s | Smooth |
| **MacBook Air M2** (16GB) | 1B (TinyLlama) | ~120 t/s | Lightning Fast |
| **Windows Desktop** (RTX 3070) | 8B (Llama 3) | ~45 t/s | Excellent |
| **Windows Laptop** (Intel Iris Xe) | 3B (Phi-3) | ~10-15 t/s | Usable/Good |
| **Windows Laptop** (Intel UHD) | 1B (Q4) | ~15 t/s | Good |

---

## 🗺️ Roadmap

We are constantly improving ResourceAI. Here is what we are working on:

- [x] **RAG (Retrieval-Augmented Generation):** Chat with your PDF, DOCX, and TXT files locally.
- [x] **Auto-Updater:** Seamless in-app updates for both the binary and the model definitions.
- [ ] **Web Search:** Allow the model to fetch real-time information from the web while maintaining privacy.
- [ ] **Custom System Prompts:** Personalized system instructions per user/conversation.
- [ ] **Local File Search:** Find files on your computer using natural language.
- [ ] **Local File Creation:** Generate and save files (code, text, reports) directly to your local storage.
- [ ] **CUDA Support (Windows):** Optional backend for NVIDIA users to unlock maximum performance.
- [ ] **Vision Models:** Support for LLaVA and other multimodal models (chat with images).
- [ ] **Linux Support:** Native .AppImage or .deb release.

---

## 🤝 Contributing

We welcome feedback! Since this is a specialized desktop application:
1. **Issues:** Please use the GitHub Issues tab to report crashes or model incompatibilities.
2. **Models:** If a specific GGUF model fails to load, please provide the HuggingFace link in your issue report.

## 📄 License

ResourceAI is proprietary software available for free during the Public Beta.
Copyright © 2026 FenixResource. All Rights Reserved.