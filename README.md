# AIDI1002 Machine Learning Programming - Final-Project
Final project for AIDI 1002 Machine Learning Programming: YOLO-FaceV2 - Implementation and contribution
# YOLO-FaceV2 – AIDI 1002 Final Project (Misba & Noor)

This project is a replication and extension of the paper:

**YOLO-FaceV2: A Scale and Occlusion Aware Face Detector (2022)**  
📄 [Paper on arXiv](https://arxiv.org/abs/2205.15270)  
🔗 [Original GitHub Repo](https://github.com/Krasjet-Yu/YOLO-FaceV2)

---

## Objective
- Reproduce the YOLO-FaceV2 face detection model.
- Train it on a reduced validation subset of the WIDER FACE dataset.
- Tweak and troubleshoot the training process to make it compatible with modern environments (PyTorch 2.6, NumPy, etc.).

---

## Implementation

Replicated the official training pipeline:
- Converted WIDER FACE annotations to YOLO format.
- Set up model and data configuration.
- Trained YOLOv5s on the val dataset for face detection.

---

## Contributions

**Experimentation on a validation subset (~500MB):**
- Created a new `data.yaml` config for it.
- Trained the model from scratch for 5 epochs.

 **Codebase Fixes:**
- Replaced deprecated `np.int` → `int`
- Fixed indexing/clamping errors in `loss.py`
- Patched PyTorch serialization errors and `autocast()` deprecation warnings

**Evaluation & Export:**
- Evaluated the model on new data
- Exported trained weights to TorchScript and ONNX

---

## Folder Structure

```
YOLO-FaceV2-FinalProject/
├── data/
├── runs/train/
├── models/
├── utils/
├── AIDI_1002_Final_Project.ipynb
├── README.md
```

---

##  How to Run This Project

### Run on Google Colab (Recommended)
1. Open [Google Colab](https://colab.research.google.com/)
2. Upload the notebook:
   - `AIDI_1002_Final_Project.ipynb`
3. Upload the required folders:
   - `data/widerface/images/val` (WIDER FACE validation subset)
   - `data/widerface/labels/val` (converted YOLO labels)
   - `data/widerface_split` (annotation files)
4. Run the notebook cell-by-cell in order after installing the dependencies.
5. Install dependencies in the first cell of the notebook if not already available:
```python
!pip install -r requirements.txt ``` 

