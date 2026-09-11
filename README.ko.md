<div align="center">

# 안녕하세요, 강민수입니다 👋

### Efficient AI · Model Compression · Computer Vision

딥러닝 모델을 **더 작고, 더 빠르게, 그러면서도 정확하게** 만들어<br/>
실제로 필요한 곳에서 돌아가게 하는 데 관심이 있습니다.

[![Email](https://img.shields.io/badge/Email-kminsoo0929%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:kminsoo0929@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-neodle-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/neodle)

[English](README.md) · **한국어**

</div>

---

## 🙋 About Me

- 🎓 **건양대학교 의료인공지능학과** 학사 과정 (2027.02 졸업 예정)<br/>
  딥러닝, 컴퓨터비전, 영상 분석을 공부했습니다. 의료영상과 실제 환경의 영상을 다루며, 모델은 정확할 뿐 아니라 *실제로 배포할 수 있을 만큼 실용적*이어야 한다는 것을 배웠습니다.
- 🔬 **ETRI 하계 연구연수생** (2026.07 ~ 2026.08)
- 📝 학술대회 논문 **3편** (공동 제1저자) · 🏆 경량 생성 모델 연구로 **우수 발표 논문상** 수상
- 🌱 **효율적인 머신러닝(Efficient AI) 분야 석사 연구 기회**를 찾고 있습니다

---

## 🎯 Research Interests

- **Model compression**: pruning, quantization, 경량 아키텍처 설계
- **Efficient vision & multimodal models**: VLM과 생성 모델의 token pruning 및 추론 가속
- **Accuracy–efficiency trade-off**: 파라미터·FLOPs·지연시간을 줄이면서 품질을 유지하는 실시간·엣지 배포
- **Applications**: 연산 자원과 지연시간이 중요한 의료·시각 AI

---

## ⚡ Why Efficient AI?

제 프로젝트에서 가장 흥미로웠던 질문은 대부분 **"품질을 유지하면서 얼마나 줄일 수 있을까?"** 였습니다.

| 작업 | 무엇을 가볍게 / 빠르게 했는가 | 결과 |
|---|---|---|
| 🌀 **Lightweight CycleGAN** | Residual block 축소(9 → 4), 채널 폭 조정, Depthwise Conv 실험 | **Params −52%**, **FLOPs −55%**, **FPS 약 1.6배**, PSNR·SSIM도 향상 |
| 🔥 **YOLOv11 화재 탐지** | 실시간 다중 분류 탐지기 설계 | mAP@50 ≈ 0.8에서 **53~67 FPS** |
| 🛏️ **Ulcer-Prevention-AI** | YOLO-Pose 위에 작은 GCN 보정 단계 추가 | 속도 손실 거의 없이 (49.91 → 49.89 FPS) PCKh@0.5 **0.628 → 0.819** |
| 🖼️ **FLUX 현지화** | 전체 fine-tuning 대신 파라미터 효율적인 LoRA, 6-step 확산 모델 사용 | 전체 모델 학습 없이 객체 변환 |

---

## 📝 Publications

### 1. FLUX 인페인팅과 다중 LoRA 조건 분리를 이용한 영상 객체 자동 변환
`2026 한국방송·미디어공학회 하계학술대회` · 공동 제1저자 · KBS 협업 · [💻 Code](https://github.com/neodle/flux-localization-pipeline-1)

> OTT 콘텐츠의 **시각 현지화**(간판·로고·제품 교체)를 자동화하는 파이프라인
- **Grounding DINO**로 텍스트 기반 객체 탐지 → **SAM**으로 픽셀 단위 마스크 생성
- 배경은 **Fill**, 참조 객체는 **Subject** 조건으로 분리하고 **Denoising LoRA**로 확산 오차 보정
- 배경의 조명·구조는 유지하면서 객체 정체성까지 보존, 가려짐(Occlusion) 상황에서도 안정적인 결과

### 2. CycleGAN 기반 색상화 성능 유지와 처리 속도 향상 🏆
`2025 KAICTS 추계학술대회` · 공동 제1저자 · **우수 발표 논문상** · [💻 Code](https://github.com/neodle/Lightweight-CycleGAN)

> 생성기 구조를 경량화해 **품질은 유지하고 속도는 올린** 흑백 이미지 색상화
- Residual block 수(9→6→4)와 채널 폭(1.0→0.25) 축소, Depthwise Conv 실험
- 4-block 모델: **Params −52%, FLOPs −55%**, FPS **169.8 → 272.9 (약 1.6배)**
- 속도는 빨라지고 PSNR 20.21 → **21.11**, SSIM 0.816 → **0.852**로 품질 지표도 향상

### 3. YOLOv11 기반 화재 다중 분류 탐지 모델 설계 및 성능 평가
`2025 KAICTS 추계학술대회` · 공동 제1저자 · [💻 Code](https://github.com/neodle/Real-Time-stage-aware--wildfire-progression-detection-based-YOLOv11)

> 기존 fire/smoke 이진 분류를 넘어 **화재 규모·연기 밀도별 5-class 탐지**
- 공개 데이터 정제 후 3,258장을 전부 수동 라벨링해 고품질 데이터셋 구축
- 평균 **mAP@50 ≈ 0.8**, **53~67 FPS**로 실시간 탐지 성능 확보

---

## 🚀 Projects

| 프로젝트 | 설명 | Stack |
|---|---|---|
| 🛏️ [**Ulcer-Prevention-AI-System**](https://github.com/neodle/Ulcer-Prevention-AI-System) | 자세 추정 + 32채널 압력 센서로 욕창 위험을 실시간 모니터링. GCN 기반 keypoint 보정으로 **PCKh@0.5 0.628 → 0.819** | YOLO-Pose, GCN, Arduino |
| 🌀 [**Lightweight-CycleGAN**](https://github.com/neodle/Lightweight-CycleGAN) | 경량화 CycleGAN 색상화 (KAICTS 우수 발표 논문상) | PyTorch |
| 🖼️ [**FLUX Localization Pipeline**](https://github.com/neodle/flux-localization-pipeline-1) | Grounding DINO + SAM + FLUX 다중 LoRA 기반 객체 자동 현지화 | FLUX, SAM, LoRA |
| 🔥 [**Wildfire Detection (YOLOv11)**](https://github.com/neodle/Real-Time-stage-aware--wildfire-progression-detection-based-YOLOv11) | 화재 규모·연기 밀도 기반 다중 분류 실시간 탐지 | YOLOv11 |
| 🎨 [**Gray-to-Color (pix2pix)**](https://github.com/neodle/Gray-to-color-colorization-pix2pix-based) | U-Net + PatchGAN 기반 흑백 사진 색상화 및 Flask 웹 데모 | PyTorch, Flask |
| ☁️ [**NCP LMS Project**](https://github.com/neodle/NCP-Yuhan-univ.LMS-Project) | NAVER Cloud 서비스를 활용한 나라장터 공공조달 업무 LMS | NCP, HTML |

---

## 📚 Paper Notes: Efficient Machine Intelligence (2026)

효율적인 AI에 관한 최신 연구를 공부하고 있습니다. **고려대학교 [Efficient Machine Intelligence Lab](https://emilab-ku.github.io/)의 2026년 논문**을 정리했습니다.<br/>
👉 **전체 노트: [paper-reviews/](paper-reviews/README.md)** (영문)

| 논문 | 학회 | 주제 |
|---|---|---|
| [ZOO-Prune: Training-Free Token Pruning via Zeroth-Order Gradient Estimation in VLMs](paper-reviews/README.md#zoo-prune) | CVPR 2026 | Token pruning · VLM |
| [VisRef: Visual Refocusing while Thinking Improves Test-Time Scaling in MLRMs](paper-reviews/README.md#visref) | CVPR 2026 | Test-time scaling · Multimodal reasoning |
| [Real-Time Visual Attribution Streaming in Thinking Model](paper-reviews/README.md#visual-attribution) | ICML 2026 **Spotlight** | Amortized attribution · Interpretability |
| [Block Recursive Transformers for Structured Parameter Sharing](paper-reviews/README.md#block-recursive) | EMNLP 2026 Findings | Parameter sharing · Compression |
| [MD-SNN: Membrane Potential-aware Distillation on Quantized SNN](paper-reviews/README.md#md-snn) | DATE 2026 | Quantization · Spiking NN |
| [MC-GRPO: Median-Centered GRPO for Small-Rollout RL](paper-reviews/README.md#mc-grpo) | Preprint | Efficient RL for LLMs |
| [SkillRet: A Large-Scale Benchmark for Skill Retrieval in LLM Agents](paper-reviews/README.md#skillret) | Preprint | Agentic AI · Retrieval |

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

| 수상 | 내용 | 기관 | 날짜 |
|---|---|---|:---:|
| 🥇 **우수 발표 논문상** | *CycleGAN기반 색상화 성능 유지와 처리 속도 향상* | 한국인공지능융합기술학회 (KAICTS) | 2025.11 |

---

## 📜 Certifications

![NCP](https://img.shields.io/badge/NCP-NAVER%20Cloud%20Professional-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![NCA](https://img.shields.io/badge/NCA-NAVER%20Cloud%20Associate-03C75A?style=for-the-badge&logo=naver&logoColor=white)
![ADsP](https://img.shields.io/badge/ADsP-데이터분석준전문가-1E5AA8?style=for-the-badge)

| 자격증 | 정식 명칭 | 발급 기관 | 취득일 |
|:---:|---|---|:---:|
| **NCP** | NAVER Cloud Platform Certified Professional | NAVER Cloud | 2026.02 |
| **NCA** | NAVER Cloud Platform Certified Associate | NAVER Cloud | 2025.05 |
| **ADsP** | 데이터분석준전문가 (Advanced Data Analytics Semi-Professional) | 한국데이터산업진흥원 | 2025.03 |

---

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=neodle&show_icons=true&hide_border=true&count_private=true)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=neodle&layout=compact&hide_border=true)

</div>
