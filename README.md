# 🎨 Kalexi-AI SketchLab



## ⚡ Project Overview

**Kalexi-AI SketchLab** is a cutting-edge web application designed to instantly transform photographs into professional-grade line art and technical outlines. By bridging the gap between high-performance **Generative AI** models and a simple **Streamlit** UI, it offers artists, architects, and designers two powerful, controllable modes for image processing. The entire application runs on the accelerated compute of **Google Colab**.

https://github.com/user-attachments/assets/5b765506-ab31-408c-b259-95cb406c1f87

![Kalexi-AI-SketchLab Screenshot](https://github.com/Mr-TarunD/Kalexi-AI-SketchLab/blob/8962cbc007171e9e51532f6e88c11a7958325b0e/HomePage.png)

![Kalexi-AI-SketchLab Screenshot](https://github.com/Mr-TarunD/Kalexi-AI-SketchLab/blob/8962cbc007171e9e51532f6e88c11a7958325b0e/InstantMode.png)

![Kalexi-AI-SketchLab Screenshot](https://github.com/Mr-TarunD/Kalexi-AI-SketchLab/blob/8962cbc007171e9e51532f6e88c11a7958325b0e/GenAIMode.png)

---

## 🚀 Key Features

* **Dual-Engine Processing:** Choose between ultra-fast math-based preview and high-fidelity deep learning extraction.
* **Controllable AI:** Utilizes sophisticated **ControlNet Preprocessors** (HED & PIDI) for clean, structural, or artistic edge maps.
* **GPU Acceleration:** Optimized to leverage **NVIDIA T4 GPUs** in Colab for near-instant (2-4 second) GenAI results.
* **Zero-Latency Preview:** The **Instant Mode** provides a 0.1s sketch using advanced OpenCV mathematics.
* **Real-time Diagnostics:** A sidebar status check instantly informs the user if the necessary GPU hardware is active.

---

## 🛠️ Technology Stack

| Component | Technology | Role in Project |
| :--- | :--- | :--- |
| **Frontend/UI** | **Streamlit** | Creates the interactive, clean, web-based user interface. |
| **AI Models** | **ControlNet Auxiliaries** (PIDI, HED) | Deep learning models trained for robust, semantic edge detection. |
| **Deep Learning** | **PyTorch** | The foundational framework managing tensors and GPU operations. |
| **Fast Processing** | **OpenCV** | Provides the classical computer vision algorithms for the `Instant Preview`. |
| **Compute Engine** | **Google Colab** | Hosts the Python environment and provides T4 GPU access. |
| **Deployment Bridge**| **LocalTunnel** | Creates the temporary public URL to access the local Streamlit app. |

---

## 📂 Quick Start: Deploying the Lab (In Google Colab)

The easiest way to run the SketchLab is by executing the code in a single Google Colab notebook.

### Step 1: Set Up the Hardware (Crucial for Speed)
In your Colab notebook:
1.  Go to **Runtime** > **Change runtime type**.
2.  Select **T4 GPU** under **Hardware accelerator**.
3.  Click **Save**.



### Step 2: Run the Installation and App Code

Paste and run the following commands in the first two cells of your Colab notebook.

**(Code from the last step would be inserted here, separated into two cells: one for installs/app definition and one for launch commands.)**

### Step 3: Access the Application

1.  **Get the Password:** The output from the final cell will print a password (your public IP address). **Copy this address.**
2.  **Open the Link:** Click the generated `loca.lt` link.
3.  **Launch:** Paste the password into the prompt to access the Kalexi-AI SketchLab UI.

---

## ⚙️ How to Use the Dual Engines

The application provides two distinct modes for different needs:

### Mode 1: ⚡ Instant (No AI)
* **Purpose:** Rapid preview, base sketching, or checking composition.
* **Process:** Uses a fast **OpenCV Color Dodge** algorithm (a mathematical trick).
* **Output:** Pencil-like sketch; runs in **~0.1 seconds** on any hardware.

### Mode 2: 🧠 GenAI Professional (Recommended)
* **Purpose:** Final high-quality line art for design, architecture, or detailed artistic studies.
* **Process:** Loads the **PIDI/HED** neural networks onto the GPU.
* **Output:** Clean, semantic edge maps. Runs in **~2-4 seconds** after the initial model download (cold start).



---

## 🛑 Troubleshooting & Optimization

| Problem | Likely Cause | Solution |
| :--- | :--- | :--- |
| **"Generating takes 45 seconds!"** | **CPU Detected.** The Colab runtime is not using the GPU. | Go to **Runtime > Change runtime type** and select **T4 GPU**. |
| **"First click is slow."** | **Model Download (Cold Start).** The AI models must be downloaded once. | This is normal. The app is downloading the ~500MB model. Subsequent generations are fast. |
| **Image is cropped/low quality.** | **Auto-Resize Logic.** The app resized a huge image to prevent memory overload. | This is a feature for stability. Use a slightly smaller image for better resolution, or increase the resize limit in the Python code. |
