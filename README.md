
# 🎨 AI Thumbnail Generator

An **AI-powered thumbnail generator** built using **Stable Diffusion** and **Gradio**.  
It creates professional, YouTube-style thumbnails from simple text prompts and captions.  

---

## 🚀 Features

- 🧠 **Generative AI** – Uses `Stable Diffusion v1.5` (or any compatible model) to create unique images from text.
- 🎨 **Customizable Styles** – Choose from 5 visual styles: `vibrant`, `dark`, `neon`, `minimal`, `epic`.
- 🖌️ **Smart Captions** – Automatically wraps and centers text with outline, box opacity, and positioning.
- ⚙️ **Adjustable Resolution** – Generate images up to 768×768 with adjustable quality steps.
- 🧱 **Gradio Web App** – Interactive interface accessible locally or via public URL (Colab supported).

---

## 🧠 What Is Generative AI?

> Generative AI refers to systems capable of **creating new content** — such as images, text, or music — by learning from large datasets.  
> In this project, a **diffusion model (Stable Diffusion)** generates unique thumbnails from your textual description.

---

## 🧩 Project Structure

```

📁 ai-thumbnail-generator/
│
├── thumbnail_app.py        # Main Gradio app with Stable Diffusion + caption overlay
├── genaithumb.ipynb        # Colab notebook version
├── requirements.txt        # Project dependencies
├── assets/                 # (Optional) sample outputs or screenshots
└── README.md               # Project documentation

````

---

## ⚙️ Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/ai-thumbnail-generator.git
cd ai-thumbnail-generator
````

### 2️⃣ Create Virtual Environment (optional but recommended)

```bash
python -m venv venv
source venv/bin/activate   # for Linux/Mac
venv\Scripts\activate      # for Windows
```

### 3️⃣ Install Dependencies

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install diffusers transformers accelerate safetensors gradio pillow numpy
```

*(If you’re on CPU, remove the first line and just install the others.)*

---

## 💻 Running the App

### ▶️ Option 1: Local Machine

```bash
python thumbnail_app.py
```

Open your browser at:

```
http://127.0.0.1:7860
```

### ☁️ Option 2: Google Colab

1. Open `genaithumb.ipynb` in Google Colab.
2. Run all cells.
3. Copy the **`.gradio.live` link** to open your app online.

---

## 🧰 Model Configuration

| Parameter              | Description                                           | Example                                    |
| ---------------------- | ----------------------------------------------------- | ------------------------------------------ |
| **Model Name**         | Stable Diffusion model ID (Hugging Face)              | `runwayml/stable-diffusion-v1-5`           |
| **Alternative Models** | SDXL, DreamShaper, RealisticVision, OpenJourney, etc. | `stabilityai/stable-diffusion-xl-base-1.0` |
| **Scheduler**          | DPM Solver Multistep                                  | Faster & more stable sampling              |
| **Chunk Size**         | Automatic attention slicing                           | Reduces VRAM usage on Colab                |
| **Device**             | CUDA if available, else CPU                           | `"cuda"` / `"cpu"`                         |

---

## 🧠 Input & Output

| Type        | Description                                                          |
| ----------- | -------------------------------------------------------------------- |
| **Inputs**  | Prompt, Caption, Style, Resolution, Steps, Colors, Position, Opacity |
| **Outputs** | Final generated thumbnail image + Status message                     |

---

## 🧠 Preprocessing

* **Prompt Enhancement** – Adds stylistic modifiers to prompts for cinematic or vibrant looks.
* **Text Wrapping** – Automatically fits captions within the image width.
* **Outline Rendering** – Draws multi-layer text outlines for readability.
* **Alpha Blending** – Merges semi-transparent background with the base image.

---

## 🧠 How It Works

1. **Text Prompt → Enhanced Prompt**
   User input is extended with stylistic details.
2. **Enhanced Prompt → Stable Diffusion Model**
   The model generates a base image.
3. **Base Image → Caption Overlay**
   Text, outline, and background box are added.
4. **Output → Gradio Interface**
   Final thumbnail previewed and downloadable.

---

## 🧱 Architecture

```
User Input → Text Enhancement → Diffusion Model → Image Generation → Caption Overlay → Output Display
```

---

## 📊 Dataset Information

* **Type**: Pre-trained generative model (no fine-tuning)
* **Training Dataset**: LAION-5B (image-text pairs)
* **Used For**: Learning the mapping between text prompts and images

---

## ⚡ Example

**Prompt:**

> "A futuristic city skyline at night with neon lights"

**Style:** Neon
**Caption:** "THE FUTURE IS HERE"
**Resolution:** 768x512
**Steps:** 30

**Output:**
A vibrant, cyberpunk-style thumbnail with glowing text.

---

## 💡 Future Improvements

* 🧩 Add SDXL Turbo for faster generation
* 🌈 Enable multiple model selection via dropdown
* 🎞️ Add animation or video thumbnail support
* 🔊 Integrate voice input for prompts

---

## 📄 License

This project is released under the **MIT License**.
Model weights follow their respective **Hugging Face / Stability AI** licenses.

---

## 🤝 Credits

* **Model**: [Stable Diffusion v1.5](https://huggingface.co/runwayml/stable-diffusion-v1-5)
* **Libraries**: [Diffusers](https://github.com/huggingface/diffusers), [Gradio](https://github.com/gradio-app/gradio), [PyTorch](https://pytorch.org/)
* **Developed By**: [Your Name](https://github.com/your-username)

---

## 🌟 Star the Repository

If you found this project useful, please ⭐ the repo to support future improvements!


