# AI Image Classifier

A simple Streamlit app that lets you upload an image and returns the top 3 predicted labels using a pre-trained MobileNetV2 model (ImageNet).

## Features
- Upload JPG or PNG images
- Uses `MobileNetV2` pretrained on ImageNet
- Shows top-3 predictions with confidence scores
- Caches model for faster repeat inferences

## Tech Stack
- Python 3.11+
- TensorFlow / Keras
- Streamlit
- OpenCV
- NumPy
- Pillow

## File Overview
```
main.py          # Streamlit app entry point
requirements.txt # Dependencies
README.md        # Documentation
```

## Setup
Create and activate a virtual environment (recommended):

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install --upgrade pip
pip install -r requirements.txt
```

## Run the App
```powershell
streamlit run main.py
```
Then open the local URL shown (usually http://localhost:8501).

## How It Works
1. Loads `MobileNetV2(weights="imagenet")`.
2. User uploads an image via Streamlit file uploader.
3. Image is resized to 224x224 and preprocessed.
4. Model predicts class probabilities.
5. Top 3 predictions are decoded and displayed.

## Changing the Model
Swap architecture in `load_model()`:
```python
from keras.applications import EfficientNetB0
model = EfficientNetB0(weights="imagenet")
```
Adjust preprocessing if needed.

## Possible Enhancements
- Batch / multiple image support
- Show probability bar chart
- Allow downloading raw JSON predictions
- Add custom fine-tuned model
- Dockerfile + deployment guide

## Troubleshooting
| Problem | Cause | Fix |
|---------|-------|-----|
| TensorFlow install fails | Outdated pip | `pip install --upgrade pip` |
| ImportError | Missing dependency | Reinstall requirements |
| Slow first prediction | Model weight download | Wait / ensure stable internet |
| Wrong predictions | Model limitation | Try clearer image / different model |

## License
Provided for learning and demonstration purposes.

---
Enjoy experimenting with computer vision! 🖼️
