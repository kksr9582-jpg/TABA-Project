# TABA-Project
# 🏆 Poster-to-Calendar AI Pipeline (YOLOv5 + OCR)

> 공모전, 대회, 설명회 등의 포스터 이미지를 업로드하면 **YOLOv5 객체 탐지**와 **EasyOCR**을 통해 제목과 접수 기한(날짜)을 자동으로 추출하여, **Flask 웹 캘린더**에 일정을 스마트하게 연동해 주는 인공지능 파이프라인 프로젝트입니다.

---

## 🚀 Key Features (주요 기능)

1. **자동 영역 감지 (YOLOv5)**
   - 포스터 이미지 내에서 제목과 날짜가 표기된 핵심 영역을 YOLOv5 모델을 통해 검출하고 크롭(`--save-crop`)합니다.
2. **텍스트 추출 (EasyOCR)**
   - 한국어와 영어가 혼용된 포스터 이미지에서도 높은 정확도로 텍스트를 인식합니다.
3. **일정 및 제목 파싱 (Smart Parsing)**
   - 추출된 텍스트 중 불필요한 단어를 필터링하고, 정규식 및 자연어 처리 로직을 통해 **제목, 시작일, 마감일**을 정규화합니다.
4. **웹 캘린더 자동 연동 (Flask + Ngrok)**
   - 파싱된 데이터를 기반으로 웹 캘린더 UI에 일정을 시각적으로 표시하고, 사용자가 직접 이벤트를 추가·관리할 수 있습니다.

---

## 🛠️ Tech Stack (기술 스택)

* **Deep Learning / AI**: PyTorch, YOLOv5, EasyOCR
* **Data Processing**: Python (`re`, `datetime`, `glob`, `os`)
* **Web Framework**: Flask, HTML/CSS (Interactive Calendar)
* **Environment**: Google Colab / Python 3.x

---

## 📂 Project Structure (프로젝트 구조)

```text
📦 poster-to-calendar
 ┣ 📂 data/                 # 포스터 이미지 및 데이터셋 저장 폴더
 ┣ 📂 yolov5/               # YOLOv5 서브모듈 및 소스코드
 ┣ 📂 runs/                 # YOLOv5 탐지 및 크롭 결과 저장 폴더
 ┣ 📜 app.py                # Flask 웹 서버 및 캘린더 연동 메인 코드
 ┗ 📜 README.md             # 프로젝트 설명서
