# 🎨 WarmCoolYolo - YOLO 기반 퍼스널 컬러 분류 모델

## 📌 프로젝트 개요

이 프로젝트는 YOLOv11-CLS 모델을 기반으로 사용자의 얼굴 이미지에서 **퍼스널 컬러(웜톤/쿨톤)** 를 분류하는 딥러닝 모델을 개발하는 것을 목표로 합니다. Roboflow를 통해 데이터를 수집 및 관리하고, Ultralytics 라이브러리를 통해 모델을 학습 및 평가합니다.

향후 FastAPI를 이용한 API 서버 개발, Unity 기반 AR 가상 메이크업 기능, 커뮤니티 기능(Photon Engine 연동) 등으로 확장할 계획입니다.

---

## 🏗 시스템 구성 요소 관계 흐름

```
[ photon chat ]
  -같은 퍼스널 컬러인 사람들 끼리 커뮤니티를 할수 있는 공간 구현

        ↑ 퍼스널 컬러 제공

[ Unity (시작점)]
  - 사용자 얼굴 이미지 촬영
  - 분석 결과 기반 AR 메이크업 적용 (ARFoundation)
  - ➕ 결과 기반으로 Photon Chat 연결

이미지 전송   ⇅결과 수신

[ FastAPI 서버 ]
  - YOLOv11-CLS 모델 호출
  - Unity에서 이미지 수신 → 추론 → 결과 응답

이미지 전송   ⇅결과 수신

[ YOLOv11-CLS 모델 (Ultralytics) ](https://docs.ultralytics.com/ko/tasks/classify/)
  - 학습된 weight로 이미지 분류
  - 퍼스널 컬러 결과 반환

        ↑ 데이터 제공

[ Roboflow & github]
  - YOLOv11-CLS 학습용 데이터셋 제공=
```

---

## 🧠 핵심 기능

- ✅ YOLOv11-CLS를 활용한 얼굴 이미지 분류
- ✅ Roboflow를 통한 데이터셋 버전 관리 및 자동 다운로드
- ✅ 학습, 평가, 시각화 전 과정이 포함된 Jupyter Notebook
- ⏳ 향후 FastAPI, Unity, Photon과의 연동 예정

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
- [Roboflow](https://roboflow.com/) (데이터셋 관리 및 로드)
- Python, Jupyter Notebook

---

## 🚀 학습 시작하기

1. Roboflow API 키를 설정하고 데이터셋을 불러옵니다.
2. \`train.ipynb\`를 실행해 YOLOv11-CLS 모델을 학습합니다.
3. \`score.ipynb\`에서 성능을 평가하고 시각화합니다.

---
