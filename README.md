<div align="center">

# Hi, I'm Minsoo Kang 👋

### Efficient AI · Model Compression · Computer Vision

I'm interested in making deep learning models **smaller, faster, and still accurate**,<br/>
so they can actually run where they are needed.

[![Email](https://img.shields.io/badge/Email-kminsoo0929%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:kminsoo0929@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-neodle-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/neodle)

**English** · [한국어](README.ko.md)

</div>

---

## 🙋 About Me

- 🔬 **Summer Research Trainee, ETRI** (Jul 1 – Aug 31, 2026)
- 🧪 **Finalist, KPS Undergraduate Physics Research Competition** (finals in Oct 2026)
- 📝 **3** conference papers (co-first author) · 🏆 **Excellent Paper Award** for a lightweight generative model
- 🌱 Currently looking for **M.S. research opportunities in efficient machine intelligence**

---

## 💼 Experience

### 🔬 Summer Research Trainee · ETRI
`Jul 1, 2026 – Aug 31, 2026` · Electronics and Telecommunications Research Institute · X-ray & Terahertz Components Research Section · Daejeon, Korea

> **Medical X-ray imaging research through Monte Carlo simulation** with **OpenGATE (Geant4)**
- **Simulation pipeline**: built baseline SPECT (Tc-99m) and X-ray CT simulations (source → phantom → detector → ROOT/image output), migrated OpenGATE v9 macros to v10 Python, and ran large-scale jobs on a GPU server
- **Contrast-enhanced mammography (K-edge subtraction)**: simulated dual-energy (LE/HE) iodine imaging with SpekPy X-ray spectra, and compared iodine CNR across tube/filter conditions and breast phantom thicknesses (20–50 mm)
- **X-ray transmission & scatter analysis**: measured Mo/Mo beam transmission and scatter through Gd₂O₃ and PETP/Gd₂O₃ stacked plate structures
- **Photon-counting CT for coronary artery disease**: built an XCAT-based heart and coronary artery phantom (iodine-enhanced blood, calcified plaque) and a PCCT scanner model to evaluate conventional, U-Net-based, and physics-guided material decomposition

### ☁️ Co-op Intern · Cloud Square Co., Ltd.
`Jul 23, 2025 – Aug 22, 2025` · 160 hours
- Cloud track: cloud configuration, architecture design, and cloud-based operations
- Carried out on-the-job tasks as a team project and presented the results

---

## 🎯 Research Interests

- **Model compression**: pruning, quantization, and lightweight architecture design
- **Efficient vision & multimodal models**: token pruning and faster inference for VLMs and generative models
- **Accuracy–efficiency trade-offs**: keeping quality while cutting parameters, FLOPs, and latency for real-time and edge deployment
- **Applications**: medical and visual AI, where compute and latency budgets really matter

---

## ⚡ Why Efficient AI?

In most of my projects, the question that interested me most was **"How much can we cut while keeping quality?"**

| Work | What I made lighter / faster | Result |
|---|---|---|
| 🌀 **Lightweight CycleGAN** | Reduced residual blocks (9 → 4), scaled channel width, tried depthwise conv | **Params −52%**, **FLOPs −55%**, **~1.6× FPS**, with PSNR and SSIM also improved |
| 🔥 **YOLOv11 Wildfire Detection** | Real-time multi-class detector design | **53–67 FPS** at mAP@50 ≈ 0.8 |
| 🛏️ **Ulcer-Prevention-AI** | Added a small GCN refinement stage on top of YOLO-Pose | PCKh@0.5 **0.628 → 0.819** at almost no speed cost (49.91 → 49.89 FPS) |
| 🖼️ **FLUX Localization** | Parameter-efficient LoRA adapters instead of full fine-tuning, with a few-step (6-step) diffusion model | Object transformation with no full-model fine-tuning |

---

## 📝 Publications

### 1. Automatic Object Transformation in Image via FLUX Inpainting with Multi-LoRA Condition Decomposition
**Minsoo Kang**†, Ayoung Jeong†, Namho Kim (KBS), Junhwa Kim‡<br/>
`KIBME 2026 Summer Conference` (The Korean Institute of Broadcast and Media Engineers) · Co-first author · In collaboration with KBS · [💻 Code](https://github.com/neodle/flux-localization-pipeline-1)

> A pipeline that automates **visual localization** of OTT content (replacing signs, logos, and products)
- Text-prompted object detection with **Grounding DINO** → pixel-level masks with **SAM**
- Background injected as the **Fill** condition, reference object as the **Subject** condition, with a **Denoising LoRA** correcting accumulated diffusion errors
- Preserves the scene's lighting and structure along with the object's identity, and stays stable under occlusion

### 2. Maintaining Colorization Quality While Improving Speed with a Lightweight CycleGAN 🏆
**Minsoo Kang**† et al. (4 authors, Konyang University)<br/>
`KAICTS 2025 Fall Conference` (Korea Artificial-Intelligence Convergence Technology Society) · Nov 2025 · Co-first author · **Excellent Paper Award** · [💻 Code](https://github.com/neodle/Lightweight-CycleGAN)

> Grayscale image colorization that **keeps quality while running faster** through a lighter generator
- Reduced residual blocks (9 → 6 → 4) and channel width (1.0 → 0.25), plus depthwise-convolution experiments
- 4-block model: **Params −52%, FLOPs −55%**, FPS **169.8 → 272.9 (~1.6×)**
- Quality metrics improved as well: PSNR 20.21 → **21.11**, SSIM 0.816 → **0.852**

### 3. Design and Performance Evaluation of a YOLOv11-based Multi-class Fire Detection Model
**Minsoo Kang**† et al. (3 authors, Konyang University)<br/>
`KAICTS 2025 Fall Conference` (Korea Artificial-Intelligence Convergence Technology Society) · Nov 2025 · Co-first author · [💻 Code](https://github.com/neodle/Wildfire-Progression-Detection)

> Going beyond binary fire/smoke detection to **5 classes by fire size and smoke density**
- Cleaned a public dataset and hand-labeled all 3,258 images to build a high-quality dataset
- Mean **mAP@50 ≈ 0.8** at **53–67 FPS**, fast enough for real-time monitoring

<sub>† equal contribution (co-first author) · ‡ corresponding author</sub>

---

## 🚀 Projects

| Project | Description | Stack |
|---|---|---|
| 🛏️ [**Ulcer-Prevention-AI-System**](https://github.com/neodle/Ulcer-Prevention-AI-System) | Real-time pressure ulcer risk monitoring with pose estimation and a 32-channel pressure sensor. GCN keypoint refinement raised **PCKh@0.5 from 0.628 to 0.819** | YOLO-Pose, GCN, Arduino |
| 🌀 [**Lightweight-CycleGAN**](https://github.com/neodle/Lightweight-CycleGAN) | Lightweight CycleGAN colorization (KAICTS Excellent Paper Award) | PyTorch |
| 🖼️ [**FLUX Localization Pipeline**](https://github.com/neodle/flux-localization-pipeline-1) | Automatic object localization with Grounding DINO + SAM + FLUX multi-LoRA | FLUX, SAM, LoRA |
| 🔥 [**Wildfire Detection (YOLOv11)**](https://github.com/neodle/Wildfire-Progression-Detection) | Real-time multi-class detection by fire size and smoke density | YOLOv11 |
| 🎨 [**Gray-to-Color (pix2pix)**](https://github.com/neodle/Gray-to-color-colorization-pix2pix-based) | Grayscale photo colorization with a U-Net + PatchGAN, plus a Flask web demo | PyTorch, Flask |
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
| 🥇 **Excellent Paper Award** | *Maintaining Colorization Quality While Improving Speed with a Lightweight CycleGAN* | Korea Artificial-Intelligence Convergence Technology Society (KAICTS) | Nov 15, 2025 |
| 🧪 **Finalist** (finals in Oct 2026) | *[Undergraduate Physics Research Competition](https://www.kps.or.kr/content/def/view.php?ft=29)* | Korean Physical Society (KPS) | Oct 2026 |

---

## 🎓 Coursework

| Course | Instructor | Host | Topics |
|---|---|---|---|
| **PyTorch Advanced Special Lecture** | [Youngwan Lee](https://github.com/youngwanLEE) — Senior Researcher at ETRI · Ph.D. student, MLAI @ KAIST | ETRI | Machine learning, Transformer, Vision Transformer (ViT) |

---

## 📜 Certifications

![NCP](https://img.shields.io/badge/NCP-NAVER%20Cloud%20Professional-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![NCA](https://img.shields.io/badge/NCA-NAVER%20Cloud%20Associate-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![ADsP](https://img.shields.io/badge/ADsP-Data%20Analytics%20Semi--Professional-1E5AA8?style=for-the-badge)

| Certification | Full Name | Issuer | Date |
|:---:|---|---|:---:|
| **NCP** | NAVER Cloud Platform Certified Professional | NAVER Cloud | Feb 5, 2026 |
| **NCA** | NAVER Cloud Platform Certified Associate | NAVER Cloud | May 23, 2025 |
| **ADsP** | Advanced Data Analytics Semi-Professional | Korea Data Agency | Mar 21, 2025 |

---

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=neodle&show_icons=true&hide_border=true&count_private=true)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=neodle&layout=compact&hide_border=true)

</div>
