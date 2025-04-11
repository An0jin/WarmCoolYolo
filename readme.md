# 🎨 WarmCoolYolo - YOLO 기반 퍼스널 컬러 분류 모델

## 📌 프로젝트 개요

이 프로젝트는 YOLOv11-CLS 모델을 기반으로 사용자의 얼굴 이미지에서 **퍼스널 컬러(웜톤/쿨톤)** 를 분류하는 딥러닝 모델을 개발하는 것을 목표로 합니다. Roboflow를 통해 데이터를 수집 및 관리하고, Ultralytics 라이브러리를 통해 모델을 학습 및 평가합니다.

향후 FastAPI를 이용한 API 서버 개발, Unity 기반 AR 가상 메이크업 기능, 커뮤니티 기능(Photon Engine 연동) 등으로 확장할 계획입니다.

---


## 🏗 시스템 구성
프로젝트는 다음 세 개의 주요 리포지토리로 구성되어 있습니다:

### 1. [WarmCoolYolo](https://github.com/anyoungjin20040106/WarmCoolYolo)
- YOLOv11-CLS 기반 퍼스널 컬러 분류 모델
- Roboflow를 통한 데이터셋 관리
- 모델 학습 및 평가 파이프라인

### 2. [WarmCoolFastapi](https://github.com/anyoungjin20040106/WarmCoolFastapi)
- FastAPI 기반 백엔드 서버
- YOLOv11-CLS 모델 서빙
- RESTful API 엔드포인트 제공
- MySQL 데이터베이스 연동

### 3. [WarmCoolUnity](https://github.com/anyoungjin20040106/WarmCoolUnity)
- Unity 기반 AR 애플리케이션
- ARFoundation을 통한 얼굴 인식
- 가상 메이크업 적용
- Photon 기반 실시간 채팅

### 4. [WarmCoolSQL](https://github.com/anyoungjin20040106/WarmCoolSQL)
- 채팅 정보 관리
- 유저 정보 관리
- 퍼스널 컬러 해설

### 5. [WarmCoolDataset](https://github.com/anyoungjin20040106/WarmCoolDataset)
- roboflow를 활용한 데이터 수집
- github를 활용한 데이터 수집
- 데이터 전처리
---

## 🗂 프로젝트 파일 구조

```
├── dataset/                    # 로컬 데이터셋 (Roboflow에서 다운로드됨)
├── data collection.ipynb       # 이미지 업로드 및 Roboflow 연동
├── data visualization.ipynb    # 데이터 통계 및 시각화
├── datamove.ipynb              # 폴더 구조 정리 및 전처리
├── train.ipynb                 # YOLOv11-CLS 모델 학습
├── score.ipynb                 # 모델 평가 및 결과 분석
└── README.md                   # 프로젝트 소개 파일
```

---

## 🛠 사용 기술

- [Ultralytics YOLOv11n-cls](https://docs.ultralytics.com/ko/tasks/classify/)
- Python, Jupyter Notebook


---

## 💻 기술 스택
- **AI/ML**: YOLOv11-CLS, Ultralytics
- **백엔드**: FastAPI, MySQL
- **프론트엔드**: Unity, ARFoundation
- **네트워킹**: Photon PUN2
- **데이터**: Roboflow
