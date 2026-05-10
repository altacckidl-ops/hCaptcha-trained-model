# hCaptcha Breakable Object Solver (YOLOv8) 🚀

A fast and lightweight YOLOv8 model trained specifically for the hCaptcha challenge:

> **"Select the object that breaks easily"**

This project provides accurate object detection with fully offline inference and millisecond response times.

---

## ✨ Features

- ⚡ Fast YOLOv8 inference
- 🧠 Trained specifically for breakable object challenges
- 🌐 Fully offline — no API required
- 🎯 Accurate bounding box detection
- 🖥️ CPU & GPU support
- 📦 Lightweight and easy to use

---

## 📊 Performance

| Metric | Score |
| :--- | :--- |
| **Precision** | 99% |
| **Recall** | 95% |
| **mAP@50** | 94% |
| **F1 Score** | 97% |

---

## 🛠️ Installation

Make sure Python 3.8+ is installed.

Install dependencies:

```bash
pip install ultralytics opencv-python
```

---

## 🚀 Quick Start

Place these files in the project directory:

- `best.pt` → trained YOLOv8 model
- `board.jpeg` → hCaptcha challenge image

Run this script:

```python
from ultralytics import YOLO

# Load trained model
model = YOLO("best.pt")

# Run inference
results = model("board.jpeg")

# Extract coordinates
for result in results:
    for box in result.boxes:
        x1, y1, x2, y2 = map(int, box.xyxy[0].tolist())

        # Calculate center point
        center_x = (x1 + x2) // 2
        center_y = (y1 + y2) // 2

        print(f"Target Found -> X: {center_x}, Y: {center_y}")
```

---

## 📷 Example Output

The model detects the correct object and returns its center coordinates for accurate targeting.

For results and more trained models join our discord
👉 [https://discord.gg/steezyteam](https://discord.gg/AzUEK4gUva)

---

## 📁 Project Structure

```bash
.
├── best.pt
├── board.jpeg
├── main.py
└── README.md
```

---

## 📄 License

This project is for educational and research purposes only.
