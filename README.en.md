<div align="center">

# Hi, I'm Minsoo Kang 👋

### Medical AI · Computer Vision · X-ray Imaging Simulation

I build **AI that doesn't miss the small signals in an image**.<br/>
My work spans medical image analysis, generative image editing, and Monte Carlo–based X-ray imaging simulation.

[![Email](https://img.shields.io/badge/Email-kminsoo0929%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:kminsoo0929@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-neodle-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/neodle)

[한국어](README.md) · **English**

</div>

---

## 🙋 About Me

- 🎓 Senior, **Dept. of Medical Artificial Intelligence, Konyang University** (Mar 2021 – Feb 2027, expected)
- 🔬 Summer Research Intern, **ETRI X-ray & Terahertz Components Research Lab** (Jul – Aug 2026)
- 📝 **3** conference papers presented · **Excellent Paper Award**
- 🎯 Interests: medical imaging AI, image generation & restoration, X-ray imaging physics simulation

---

## 📝 Publications

### 1. Automatic Object Transformation in Image via FLUX Inpainting with Multi-LoRA Condition Decomposition
`KIBME 2026 Summer Conference` · Co-first author · In collaboration with KBS · [💻 Code](https://github.com/neodle/flux-localization-pipeline-1)

> A pipeline that automates **visual localization** of OTT content (replacing signs, logos, and products)
- Text-prompted object detection with **Grounding DINO** → pixel-level masks with **SAM**
- Background injected as the **Fill** condition, reference object as the **Subject** condition, with a **Denoising LoRA** correcting accumulated diffusion errors
- Preserves the scene's lighting and structure along with the object's identity, and stays stable under occlusion

### 2. Maintaining Colorization Quality While Improving Speed with a Lightweight CycleGAN 🏆
`KAICTS 2025 Fall Conference` · Co-first author · **Excellent Paper Award** · [💻 Code](https://github.com/neodle/Lightweight-CycleGAN)

> Grayscale image colorization that **keeps quality while running faster** through a lighter generator
- Reduced residual blocks (9 → 6 → 4) and channel width (1.0 → 0.25), plus depthwise-convolution experiments
- 4-block model: **Params −52%, FLOPs −55%**, FPS **169.8 → 272.9 (~1.6×)**
- Quality metrics improved as well: PSNR 20.21 → **21.11**, SSIM 0.816 → **0.852**

### 3. Design and Performance Evaluation of a YOLOv11-based Multi-class Fire Detection Model
`KAICTS 2025 Fall Conference` · Co-first author · [💻 Code](https://github.com/neodle/Real-Time-stage-aware--wildfire-progression-detection-based-YOLOv11)

> Going beyond binary fire/smoke detection to **5 classes by fire size and smoke density**
- Cleaned a public dataset and hand-labeled all 3,258 images to build a high-quality dataset
- Mean **mAP@50 ≈ 0.8** at **53–67 FPS**, fast enough for real-time monitoring

---

## 🔬 Research Experience — ETRI Summer Research Intern

**Electronics and Telecommunications Research Institute (ETRI), X-ray & Terahertz Components Research Lab** · Jul – Aug 2026<br/>
Project: *Developing an X-ray imaging technique that detects malignant breast microcalcifications in a single shot*

| Topic | Work |
|---|---|
| **Monte Carlo simulation setup** | Built SPECT and X-ray simulations on OpenGATE v10 (Geant4), ported v9 macros to Python, and wrote the team's setup guide |
| **X-ray spectrum modeling** | Generated and validated spectra with SpekPy matched to a real X-ray tube (Hamamatsu microfocus source) |
| **K-edge subtraction imaging** | Modeled a breast-equivalent phantom with iodine objects at several concentrations; analyzed CNR across spectrum pairs (W/W, Mo/Rh) and phantom thicknesses |
| **Material transmission & scatter** | Analyzed X-ray transmission and scatter in stacked Gd₂O₃ / PETP plates; computed absorbed dose (Dose/Thermal Actor) and breast MGD |
| **Cardiovascular PCCT simulation** | Built XCAT-based chest, heart, and coronary artery phantoms (3D Slicer, mesh Boolean), designed photon-counting CT scan conditions, and set energy thresholds via CRLB |
| **Literature review** | Surveyed low-dose iodine protocols in cardiac CTA; compared material decomposition methods (conventional / U-Net / physics-guided) |

> I documented experiment design, results, and how I addressed feedback in daily reports, and ran large-scale simulations on a remote GPU server (H200).

---

## 🚀 Projects

| Project | Description | Stack |
|---|---|---|
| 🛏️ [**Ulcer-Prevention-AI-System**](https://github.com/neodle/Ulcer-Prevention-AI-System) | Real-time pressure ulcer risk monitoring with pose estimation and a 32-channel pressure sensor. GCN keypoint refinement raised **PCKh@0.5 from 0.628 to 0.819** | YOLO-Pose, GCN, Arduino |
| 🎨 [**Gray-to-Color (pix2pix)**](https://github.com/neodle/Gray-to-color-colorization-pix2pix-based) | Grayscale photo colorization with a U-Net + PatchGAN, plus a Flask web demo | PyTorch, Flask |
| 🌀 [**Lightweight-CycleGAN**](https://github.com/neodle/Lightweight-CycleGAN) | Lightweight CycleGAN colorization (KAICTS Excellent Paper Award) | PyTorch |
| 🖼️ [**FLUX Localization Pipeline**](https://github.com/neodle/flux-localization-pipeline-1) | Automatic object localization with Grounding DINO + SAM + FLUX multi-LoRA | FLUX, SAM, LoRA |
| 🔥 [**Wildfire Detection (YOLOv11)**](https://github.com/neodle/Real-Time-stage-aware--wildfire-progression-detection-based-YOLOv11) | Real-time multi-class detection by fire size and smoke density | YOLOv11 |
| ☁️ [**NCP LMS Project**](https://github.com/neodle/NCP-Yuhan-univ.LMS-Project) | LMS built on NAVER Cloud services to streamline public procurement on the Nara Marketplace | NCP, HTML |

---

## 🛠️ Tech Stack

**AI / Vision**<br/>
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![YOLO](https://img.shields.io/badge/YOLO-0B23A9?style=flat-square&logo=yolo&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

**Medical Imaging / Simulation**<br/>
![OpenGATE](https://img.shields.io/badge/OpenGATE-Geant4-005F87?style=flat-square)
![SpekPy](https://img.shields.io/badge/SpekPy-X--ray%20Spectrum-6A5ACD?style=flat-square)
![3D Slicer](https://img.shields.io/badge/3D%20Slicer-1F65B0?style=flat-square)
![ROOT](https://img.shields.io/badge/ROOT-CERN-2F6FAE?style=flat-square)

**Infra / Tools**<br/>
![NAVER Cloud](https://img.shields.io/badge/NAVER%20Cloud-03C75A?style=flat-square&logo=naver&logoColor=white)
![Linux](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude%20Code-D97757?style=flat-square&logo=anthropic&logoColor=white)

---

## 🏆 Awards

| Award | Paper | Organization | Date |
|---|---|---|:---:|
| 🥇 **Excellent Paper Award** | *Maintaining Colorization Quality While Improving Speed with a Lightweight CycleGAN* | Korea Artificial-Intelligence Convergence Technology Society (KAICTS) | Nov 2025 |

---

## 📜 Certifications

![NCP](https://img.shields.io/badge/NCP-NAVER%20Cloud%20Professional-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![NCA](https://img.shields.io/badge/NCA-NAVER%20Cloud%20Associate-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![ADsP](https://img.shields.io/badge/ADsP-Data%20Analytics%20Semi--Professional-1E5AA8?style=for-the-badge)

| Certification | Full Name | Issuer | Date |
|:---:|---|---|:---:|
| **NCP** | NAVER Cloud Platform Certified Professional | NAVER Cloud | Feb 2026 |
| **NCA** | NAVER Cloud Platform Certified Associate | NAVER Cloud | May 2025 |
| **ADsP** | Advanced Data Analytics Semi-Professional | Korea Data Agency | Mar 2025 |

---

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=neodle&show_icons=true&hide_border=true&count_private=true)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=neodle&layout=compact&hide_border=true)

</div>
