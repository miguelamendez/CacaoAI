---
layout: post
title: "Running DeepSeek-R1 on Ubuntu with llama.cpp"
description: "This tutorial will guide you through installing `llama.cpp` and running the DeepSeek-R1 model locally on a Debian Distro. The process involves cloning the repository, configuring the build based on your hardware, and setting up the server to run the model."
date: 2025-04-09
header_image: "/assets/images/llamacpp.png"
categories: [llm,llamacpp,deepseekr1,shell]
---

## Prerequisites

Before starting, ensure you have the following installed on your system:

### System Dependencies

1. **Git**: For cloning the repository.
   ```sh
   sudo apt-get install git
   ```
2. **CMake**: For building the project.
   ```sh
   sudo apt-get install cmake
   ```
3. **Build Essentials**: Required for compiling the project.
   ```sh
   sudo apt-get install build-essential
   ```
4. **CUDA (Optional)**: If you plan to use CUDA-enabled GPUs.
   - Install CUDA toolkit from [NVIDIA's official website](https://developer.nvidia.com/cuda-toolkit).

### Tools for Downloading the Model

- **wget or Hugging Face CLI**: To download the model.

---

## Step-by-Step Installation

### Step 1: Clone the Repository

First, clone the `llama.cpp` repository to your local machine.
```sh
git clone https://github.com/ggml-org/llama.cpp.git
```

### Step 2: Navigate to the Repository Directory

Change directory to the cloned repository.
```sh
cd llama.cpp
```

### Step 3: Pull the Latest Changes

Ensure you have the latest version of the code.
```sh
git pull
```

### Step 4: Choose Hardware Configuration

Select the appropriate build configuration based on your hardware.

#### For CPU Only
```sh
cmake -B build
```

#### For CUDA GPU

If you have CUDA installed and want to leverage GPU acceleration:
```sh
cmake -B build -DGGML_CUDA=ON
```

### Step 5: Build the Project

Compile the project with the chosen configuration.
```sh
cmake --build build --config Release
```

**Note:** The build process may take several minutes, depending on your system's performance.

### Step 6: Copy Binaries to the Bin Directory

After a successful build, copy the generated binaries to a directory of your choice (e.g., `~/bin`).
```sh
mkdir -p ~/bin
cp build/bin/* ~/bin/
```

### Step 7: Download the DeepSeek-R1 Model

The DeepSeek-R1 model is available on Hugging Face. Use `wget` or the Hugging Face CLI to download it. For this tutorial, we will download the small 1.5B parameters version.

1. First, create the model directory:
   ```sh
   mkdir -p ~/.local/share/llama.cpp/models
   ```

2. Download the model:
   ```sh
   wget https://huggingface.co/bartowski/DeepSeek-R1-Distill-Qwen-1.5B-GGUF/resolve/main/DeepSeek-R1-Distill-Qwen-1.5B-Q8_0.gguf -O ~/.local/share/llama.cpp/models/DeepSeek-R1-Distill-Qwen-1.5B-Q8_0.gguf
   ```

---

## Step 8: Run the Server

1. Navigate to your bin directory:
   ```sh
   cd ~/bin
   ```

2. Run the server with the following command:
   ```sh
   ./llama-server \
     --model ~/.local/share/llama.cpp/models/DeepSeek-R1-Distill-Qwen-32B-Q6_K.gguf \
     --ctx-size 32000 \
     --host 127.0.0.1 \
     --port 8080 \
     --main-gpu 0 \
     --gpu-layers 90
   ```

**Parameters:**
- `--model`: Path to the DeepSeek-R1 model file.
- `--ctx-size`: Context window size (adjust as needed).
- `--host`: Server host address (default: localhost).
- `--port`: Server port (default: 8080).
- `--main-gpu`: Used for multi-GPU for inference.
- `--gpu-layers`: Number of layers to offload to GPU (adjust based on your GPU's VRAM).

---

## Step 9: Verify the Installation

1. Ensure the server is running without errors.
2. You can access the chat UI at `http://localhost:8080` to chat with the model.

---

## Troubleshooting

- **Build Errors**: Ensure all dependencies are installed and your CUDA setup is correct.
- **Permission Issues**: Use `sudo` where necessary or adjust file permissions.
- **CUDA Not Detected**: Verify CUDA is installed and properly configured on your system.
- **Model Not Found**: Double-check the model path and ensure the file exists.

---

## Conclusion

You have successfully installed `llama.cpp` and set up the DeepSeek-R1 model to run locally. The server is now ready to serve requests at `http://localhost:8080`. You can use the chat interface in the link to interact with the model.

**Note:** Replace placeholders like `~/bin` and `~/.local/share/llama.cpp/models` with your actual directory paths as needed.

Enjoy exploring the capabilities of DeepSeek-R1 with `llama.cpp`!
