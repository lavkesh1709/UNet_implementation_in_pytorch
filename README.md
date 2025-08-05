# UNet_implementation_in_pytorch

# 🎨 Polygon Coloring using U-Net

This project aims to color segmented polygon regions in images using a U-Net-based semantic segmentation model. It uses PyTorch for model building and training, and [Weights & Biases (W&B)](https://wandb.ai/) for experiment tracking and model versioning.

> Think of it like a smart coloring book — but for structured data, polygons, and deep learning 🤖🖍️


## 🚀 Project Highlights

- 🔧 Custom PyTorch Dataset for polygons
- 🧠 U-Net architecture with 6-channel input & 3-channel RGB output
- 📈 Model training tracked using Weights & Biases
- 🏆 Best model saved & versioned via W&B Artifacts
- 🧪 Inference-ready with sample notebooks
- 🔁 Easily reproducible for other users

---

## 📁 Folder Structure

```
.
├── model.py                  # U-Net model definition
├── train_model.ipynb        # Model training notebook (with W&B logging)
├── inference.ipynb          # Inference notebook (loads model from W&B)
├── dataset.zip              # Zipped dataset (training + validation)
├── assets/
│   └── sample_image.png     # Sample polygon + output image
├── README.md                # You're here!
```

---

## 🛠️ Setup Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/polygon-coloring-unet.git
   cd polygon-coloring-unet
   ```

2. **Install dependencies**
   > It's recommended to use a virtual environment or Colab.
   ```bash
   pip install -r requirements.txt
   ```

3. **Login to Weights & Biases**
   ```bash
   wandb login
   ```

4. **Unzip dataset (if running locally)**
   ```bash
   unzip dataset.zip
   ```

---

## 🎓 How to Train

Open and run `train_model.ipynb`:

- Loads dataset
- Augments & preprocesses data
- Trains the U-Net model
- Logs all metrics to W&B
- Uploads final model as a W&B Artifact

> Make sure you’re connected to a GPU if running locally or use [Google Colab](https://colab.research.google.com/).

---

## 🔎 How to Run Inference

Open and run `inference.ipynb`:

- Downloads model artifact from W&B
- Loads U-Net model and weights
- Performs prediction on a sample polygon image
- Shows predicted color output vs. target

> No need to download `.pth` manually. It’s loaded via:
```python
wandb.use_artifact("unet_polygon_color:v0", type="model")
```

---

## 🔐 Access Requirements

✅ If you want others to reproduce:
- Make sure your W&B **project and artifact are public**.
- Go to your artifact page → ⚙️ Settings → Set visibility to `Public`.

---

## 📊 Example Output

| Target Image | Predicted Output |
|--------------|------------------|
| ![target](assets/sample_image.png) | ![output](assets/sample_output.png) |

---

## 🧠 Model Architecture

Based on the classic **U-Net** with:
- `in_channels = 6` (polygon features)
- `out_channels = 3` (RGB output)

The model learns spatial and contextual cues to fill colors inside polygonal shapes.

---

## 🧩 Tech Stack

- **PyTorch** – Model building & training
- **Weights & Biases** – Experiment tracking & artifact management
- **OpenCV / PIL** – Image preprocessing
- **Google Colab** – Runtime environment

---

## 💬 Credits & Acknowledgments

Project by [Lavkesh](https://wandb.ai/lavkesh1709-maulana-azad-national-institute-of-technolog).  
Built as a part of research/academic exploration in semantic segmentation for structured graphics and polygonal data.

---

## 📌 To-Do (Optional Features)

- [ ] Add support for polygon outlines
- [ ] Convert trained model to ONNX or TorchScript
- [ ] Deploy as an interactive coloring web app

---

## ⭐️ If this helped you…

Drop a ⭐ on the repo, tag me on W&B, or remix this project into your own creation 🎨💡  
Let’s color the world with AI 🚀