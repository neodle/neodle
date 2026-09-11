<div align="center">

# 안녕하세요, 강민수입니다 👋

### Medical AI · Computer Vision · X-ray Imaging Simulation

**영상 속 작은 신호를 놓치지 않는 AI**를 연구합니다.<br/>
의료영상 분석부터 생성형 이미지 편집, Monte Carlo 기반 X선 영상 시뮬레이션까지 다뤄 왔습니다.

[![Email](https://img.shields.io/badge/Email-kminsoo0929%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:kminsoo0929@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-neodle-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/neodle)

</div>

---

## 🙋 About Me

- 🎓 **건양대학교 의료인공지능학과** 4학년 (2021.03 ~ 2027.02 졸업 예정)
- 🔬 **ETRI 엑스선·테라헤르츠부품연구실** 하계 연구연수생 (2026.07 ~ 2026.08)
- 📝 학술대회 논문 **3편** 발표 · **우수 발표 논문상** 수상
- 🎯 관심 분야: 의료영상 AI, 영상 생성·복원, X선 영상 물리 시뮬레이션

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

## 🔬 Research Experience — ETRI 하계 연구연수생

**한국전자통신연구원(ETRI) 엑스선·테라헤르츠부품연구실** · 2026.07 ~ 2026.08<br/>
과제: *한 장의 촬영으로 악성 유방 미세석회를 발견할 수 있는 엑스선 영상 기술 개발*

| 주제 | 수행 내용 |
|---|---|
| **Monte Carlo 시뮬레이션 환경** | OpenGATE v10(Geant4) 기반 SPECT·X-ray 시뮬레이션 구축, v9 매크로 → Python 전환, 팀 설치 가이드 작성 |
| **X선 스펙트럼 모델링** | SpekPy로 실제 X선관(Hamamatsu 마이크로포커스) 사양에 맞춘 스펙트럼 생성 및 검증 |
| **K-edge Subtraction 영상** | 유방 등가 팬텀 + 아이오딘 농도별 객체 모델링, 스펙트럼 조합(W/W, Mo/Rh) 및 팬텀 두께에 따른 CNR 분석 |
| **소재 투과·산란 분석** | Gd₂O₃ / PETP 적층 판 구조의 X선 투과·산란, 흡수선량(Dose/Thermal Actor) 및 유방 MGD 산출 |
| **심혈관 PCCT 시뮬레이션** | XCAT 기반 흉부·심장·관상동맥 팬텀 제작(3D Slicer, Mesh Boolean), Photon-counting CT 촬영 조건 설계, CRLB 기반 에너지 threshold 설정 |
| **문헌 조사** | 심혈관 CTA 저용량 아이오딘 프로토콜 조사, Material Decomposition(Conventional / U-Net / Physics-guided) 비교 |

> 매일 Daily Report로 실험 설계·결과·피드백 반영 과정을 정리했고, 대규모 시뮬레이션은 원격 GPU 서버(H200)에서 수행했습니다.

---

## 🚀 Projects

| 프로젝트 | 설명 | Stack |
|---|---|---|
| 🛏️ [**Ulcer-Prevention-AI-System**](https://github.com/neodle/Ulcer-Prevention-AI-System) | 자세 추정 + 32채널 압력 센서로 욕창 위험을 실시간 모니터링. GCN 기반 keypoint 보정으로 **PCKh@0.5 0.628 → 0.819** | YOLO-Pose, GCN, Arduino |
| 🎨 [**Gray-to-Color (pix2pix)**](https://github.com/neodle/Gray-to-color-colorization-pix2pix-based) | U-Net + PatchGAN 기반 흑백 사진 색상화 및 Flask 웹 데모 | PyTorch, Flask |
| 🌀 [**Lightweight-CycleGAN**](https://github.com/neodle/Lightweight-CycleGAN) | 경량화 CycleGAN 색상화 (KAICTS 우수 발표 논문상) | PyTorch |
| 🖼️ [**FLUX Localization Pipeline**](https://github.com/neodle/flux-localization-pipeline-1) | Grounding DINO + SAM + FLUX 다중 LoRA 기반 객체 자동 현지화 | FLUX, SAM, LoRA |
| 🔥 [**Wildfire Detection (YOLOv11)**](https://github.com/neodle/Real-Time-stage-aware--wildfire-progression-detection-based-YOLOv11) | 화재 규모·연기 밀도 기반 다중 분류 실시간 탐지 | YOLOv11 |
| ☁️ [**NCP LMS Project**](https://github.com/neodle/NCP-Yuhan-univ.LMS-Project) | NAVER Cloud 서비스를 활용한 나라장터 공공조달 업무 LMS | NCP, HTML |
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
