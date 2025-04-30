
# WarmCool YOLO 이미지 분류 API

YOLO 모델을 사용한 이미지 분류 API 서비스입니다.

## 설치 방법

1. 필요한 패키지 설치:
```bash
pip install -r requirements.txt
```

2. YOLO 모델을 Keras 형식으로 변환:
```bash
python save_keras_model.py
```
이 과정을 통해 best.pt 파일이 best.keras 파일로 변환됩니다.

## API 서버 실행

```bash
python app.py
```

서버는 기본적으로 http://localhost:8000 에서 실행됩니다.

## API 사용 방법

### 웹 인터페이스 사용

1. 브라우저에서 http://localhost:8000/docs 접속
2. `/predict/` 엔드포인트 선택
3. "Try it out" 버튼 클릭
4. 이미지 파일 업로드
5. "Execute" 버튼 클릭

### cURL 사용

```bash
curl -X POST "http://localhost:8000/predict/" -H "accept: application/json" -H "Content-Type: multipart/form-data" -F "file=@이미지경로.jpg"
```

### Python 예제

```python
import requests

url = "http://localhost:8000/predict/"
files = {"file": open("이미지경로.jpg", "rb")}
response = requests.post(url, files=files)
print(response.json())
```

## API 응답 형식

```json
{
  "filename": "업로드된파일명.jpg",
  "predicted_class": "예측된클래스명",
  "confidence": 0.95,
  "class_probabilities": {
    "class_0": 0.01,
    "class_1": 0.02,
    "class_2": 0.95,
    "class_3": 0.02
  }
}
```

## 설정 변경

`app.py` 파일에서 다음 항목을 수정할 수 있습니다:

1. `MODEL_PATH`: Keras 모델 파일 경로
2. `class_names`: 클래스 이름 목록 (실제 클래스 이름으로 업데이트 필요)
3. 이미지 전처리 함수에서 이미지 크기와 정규화 방법
