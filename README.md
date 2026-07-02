[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/vboussot/SlicerImpactSeg/blob/main/LICENSE)
[![Paper](https://img.shields.io/badge/📌%20Paper-KonfAI-blue)](https://arxiv.org/abs/2508.09823)

# 🧠 Slicer IMPACT-Seg

<img src="ImpactSeg.png" alt="IMPACT Seg Logo" width="300" align="right">

**Slicer IMPACT-Seg** is an open-source 3D Slicer extension dedicated to deep learning-based **anatomical segmentation**.
It provides a unified integration of KonfAI segmentation apps within the 3D Slicer environment, making state-of-the-art segmentation models as well as quality-assurance (QA) tools accessible for routine clinical practice and research workflows.

The extension gives direct access to segmentation apps such as **ImpactSeg**, **MRSegmentator** and **TotalSegmentator**, and is powered by **KonfAI**, a modular deep learning framework ensuring **fast inference**, **reproducibility**, and **flexible deployment** into clinical workflows.

---

## ✅ What you can do in 3 minutes (step-by-step tutorial)

This quick tutorial demonstrates the typical workflow: **load → run segmentation → review results → assess reliability**.

### 1) Install and open the module
1. Install **3D Slicer ≥ 5.10**
2. Open **3D Slicer** and go to **Extension Manager**
3. Search for **ImpactSeg**
4. Click **Install**
5. Restart Slicer and open the **Impact Seg** module from the **Segmentation** category

### 2) Load a case
1. In Slicer, click **DICOM** (or drag-and-drop a NIfTI / NRRD / MHA file)
2. Load a volume (e.g., `volume.nii.gz`)
3. Confirm the volume appears in the **Data** module and is visible in the slice views

### 3) Run segmentation
1. In the Impact Seg module, open the **Segmentation** tab
2. Select:
   - **Input volume**: `volume`
   - **KonfAI App**: choose an app (e.g., *ImpactSeg*, *MRSegmentator* or *TotalSegmentator*)
3. Click **Run**
4. Wait for completion: once the process finishes, the segmentation is automatically loaded with anatomical labels and colors, and can be displayed in 3D

✅ You can now inspect the results in 2D and 3D and adjust visualization (opacity, label colors, 3D rendering).

### 4) QA with reference
If you have a reference segmentation, you can quantitatively validate the result:

1. Load the reference segmentation (as a labelmap)
2. Go to the **Evaluation** tab
3. Select:
   - **Output volume** -> the generated segmentation
   - **Reference volume** -> the reference labelmap
   - Optional **ROI mask**
4. Click **Run**
5. Review quantitative metrics and qualitative overlays inside Slicer

### 5) QA without reference (uncertainty estimation)
When no ground truth annotation is available, you can still assess prediction reliability.

1. Go to the **Evaluation** tab and select **No reference (Uncertainty)**
2. Select the **inference stack volume** generated during prediction
3. Click **Run**
4. Review the generated uncertainty maps and metrics

Uncertainty can be computed using:
- test-time augmentation (TTA)
- stochastic dropout
- multi-model ensembling

These strategies are **configurable during the segmentation step** via the **sampling settings**.

## ⚙️ Features

### 🧩 Deep Learning Inference
- Anatomical segmentation of CT, MRI and CBCT volumes
- Supports **DICOM**, **NIfTI** (`.nii`, `.nii.gz`), and **MHA** formats
- Automatic preprocessing and intensity normalization

### ⚕️ Quality Assurance (QA)
- Quantitative metrics against a reference segmentation
- Synchronized **2D/3D visual inspection** within Slicer

### 📉 Uncertainty Quantification
- Ensemble and test-time augmentation (TTA) strategies
- Voxel-wise uncertainty maps when no reference is available

### 💡 Integration-Ready
- Built on the **KonfAI** extension: shared remote computation servers, device selection and app management
- Each KonfAI App is a self-contained workflow (YAML configs + trained model) that runs identically from Python, the CLI, or this Slicer module

## 🔗 Related projects

- [KonfAI](https://github.com/vboussot/KonfAI) — the deep learning framework powering the apps
- [SlicerKonfAI](https://github.com/vboussot/SlicerKonfAI) — the base Slicer extension
- [SlicerImpactSynth](https://github.com/vboussot/SlicerImpactSynth) — synthetic CT generation
- [SlicerImpactReg](https://github.com/vboussot/SlicerImpactReg) — image registration

## 📖 Citation

If you use ImpactSeg in your research, please cite:

> Boussot V., Dillenseger J.-L.
> **KonfAI: A Modular and Fully Configurable Framework for Deep Learning in Medical Imaging.**
> [arXiv:2508.09823](https://arxiv.org/abs/2508.09823)
