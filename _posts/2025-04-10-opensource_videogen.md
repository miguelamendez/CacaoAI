---
layout: post
title: "A Survey on Current Open Source Models for Video Generation"
description: "Video generation has seen remarkable advancements in recent years, with open-source models playing a pivotal role in democratizing access to cutting-edge AI capabilities. This blog post explores the current state of open-source video generation models, their capabilities, and the companies behind them."
date: 2025-04-10
header_image: "/assets/images/cacaoai_cover.png"
categories: [t2v,i2v,opensource]
---

## 1. **LTX-Video**

### **Company & Origin**
- Developed by **Lightricks**, a company based in **Israel**.
- **Release Date**: March 5, 2025.

### **Capabilities**
- **Text-to-Video, Image-to-Video, and Keyframe-based Animation**: Supports a wide range of video generation tasks.
- **Real-time Generation**: Produces 5 seconds of 24 FPS video at 768x512 resolution in just 2 seconds on an Nvidia H100 GPU.
- **High Compression Ratio**: Achieves a 1:192 compression ratio with spatiotemporal downscaling of 32 x 32 x 8 pixels per token.
- **Fine Detail Preservation**: The VAE decoder handles both latent-to-pixel conversion and final denoising, preserving fine details.

### **License**
- **OpenRail-M**: Allows commercial use under certain conditions.

### **Links**
- [GitHub Repository](https://github.com/Lightricks/LTX-Video)
- [Hugging Face](https://huggingface.co/Lightricks/LTX-Video)
- [Research Paper](https://arxiv.org/abs/2501.00103)

---

## 2. **HunyuanVideo**

### **Company & Origin**
- Developed by **Tencent**, a Chinese technology company.
- **Release Date**: December 2024.

### **Capabilities**
- **Large-Scale Model**: Trained with over 13 billion parameters, making it the largest open-source video generation model.
- **High Visual Quality**: Produces videos with excellent text-video alignment and advanced filming techniques.
- **Image-to-Video Generation**: Supports the generation of videos from images with LoRA training for customizable effects.

### **License**
- **Tencent Hunyuan Community License**: Non-commercial use is allowed, with restrictions in the European Union, the United Kingdom, and South Korea.

### **Links**
- [GitHub Repository](https://github.com/Tencent/HunyuanVideo)
- [Hugging Face](https://huggingface.co/tencent/HunyuanVideo)
- [Research Paper](https://arxiv.org/abs/2412.03603)

---

## 3. **CogVideoX**

### **Company & Origin**
- Developed by **THUDM (Tsinghua University)**, a research institution in China.
- **Release Date**: August 27, 2024.

### **Capabilities**
- **Text-to-Video Generation**: Generates 10-second continuous videos aligned with text prompts at 16 FPS and 768x1360 resolution.
- **3D Variational Autoencoder (VAE)**: Improves compression and fidelity for both spatial and temporal dimensions.
- **Progressive Training**: Enhances the generation of coherent, long-duration videos with significant motion dynamics.

### **License**
- **Apache 2.0 License**: For the CogVideoX-2B model.
- **CogVideoX License**: For the CogVideoX-5B model.

### **CogVideoXLicense**
This license grants a non-exclusive, royalty-free, and non-transferable right to use the CogVideoX model for academic research and, with registration, for commercial purposes under specific conditions. Commercial use requires obtaining a basic license, allowing free usage up to 1 million monthly users, with additional licenses needed for higher usage. The software cannot be used for military, illegal, or harmful purposes, or for actions that harm China's interests. The software is provided "as is" without warranties, and the licensor disclaims liability for any damages. Disputes are governed by Chinese law and resolved in Beijing's Haidian District Court. The license may be updated, and inquiries should be directed to the provided contact.
1. 

### **Links**
- [GitHub Repository](https://github.com/THUDM/CogVideo)
- [Hugging Face](https://huggingface.co/THUDM/CogVideoX1.5-5B)
- [Research Paper](https://arxiv.org/pdf/2408.06072)

---

## 4. **Wan2.1**

### **Company & Origin**
- Developed by **Wan-AI**, a Chinese AI research company.
- **Release Date**: 2025.

### **Capabilities**
- **Multi-Task Support**: Excels in text-to-video, image-to-video, video editing, text-to-image, and video-to-audio generation.
- **Consumer-Grade GPU Compatibility**: The T2V-1.3B model requires only 8.19 GB of VRAM, making it accessible for most consumer-grade GPUs.
- **Text Generation**: Unique capability to generate both Chinese and English text within videos.

### **License**
- **Apache 2.0 License**: For personal and commercial use. Encourages open research and democratizes access to state-of-the-art AI capabilities.


### **Links**
- [GitHub Repository](https://github.com/Wan-Video/Wan2.1)
- [Hugging Face](https://huggingface.co/Wan-AI/Wan2.1-T2V-14B-Diffusers)
- [Research Paper](https://github.com/Wan-Video/Wan2.1)

---

## 5. **Mochi**

### **Company & Origin**
- Developed by **Genmo**, a US-based AI research company.
- **Release Date**: 2024.

### **Capabilities**
- **High-Quality Motion**: Demonstrates dramatic improvements in motion quality and strong prompt adherence.
- **Open Source**: Licensed under the Apache 2.0 license for personal and commercial use.
- **Hosted Playground**: Available for free on [Genmo.ai/play](https://genmo.ai/play).

### **License**
- **Apache 2.0 License**:For personal and commercial use. Encourages open research and democratizes access to state-of-the-art AI capabilities.


### **Links**
- [GitHub Repository](https://github.com/genmoai/mochi)
- [Hugging Face](https://huggingface.co/genmo/mochi-1-preview)
- [Research Paper](https://github.com/genmoai/mochi)

---
## Summary Table

| **Model**      | **Resolution**           | **License**                     | **Year Created** | **Country of Origin** |
|-----------------|--------------------------|---------------------------------|------------------|-----------------------|
| LTX-Video       | 768x512                 | OpenRail-M                     | 2025             | Israel                |
| HunyuanVideo    | Variable                 | Tencent Hunyuan Community License | 2024             | China                 |
| CogVideoX-5B    | 720x480                  | CogVideoX License              | 2024             | China                 |
| CogVideoX-5B-I2V| 768x1360                 | CogVideoX License              | 2024             | China                 |
| Wan2.1          | 480P, 720P               | Apache 2.0                     | 2025             | China                 |
| Mochi           | 480P (Base), HD (Coming) | Apache 2.0                     | 2024             | United States         |

Only Apache Licenses are truly [OpenSource](https://opensource.org/osd) .

---

## Conclusion

The landscape of open-source video generation is undergoing a transformative phase, driven by innovative models such as LTX-Video, HunyuanVideo, CogVideoX, Wan2.1, and Mochi. These models not only showcase impressive capabilities in video generation but also play a crucial role in democratizing access to AI technologies. Among these, models released under the Apache 2.0 license, like Wan2.1 and Mochi, stand out as fully open-source, enabling unrestricted experimentation and innovation.

---

## Further Reading

- [LTX-Video GitHub](https://github.com/Lightricks/LTX-Video)
- [HunyuanVideo GitHub](https://github.com/Tencent/HunyuanVideo)
- [CogVideoX GitHub](https://github.com/THUDM/CogVideo)
- [Wan2.1 GitHub](https://github.com/Wan-Video/Wan2.1)
- [Mochi GitHub](https://github.com/genmoai/mochi)

---
