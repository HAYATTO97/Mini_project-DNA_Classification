#  ΔG(cf) - ΔG(lin) 예측를 위한 미니 프로젝트

## 프로젝트 개요
본 프로젝트는 세종대학교 대학원 강의 '생명과학을 위한 머신러닝 응용 및 실습'의 외국인 미니 프로젝트를 돕기 위해 진행하였습니다. 이 프로젝트에서는 DNA 시퀀스를 인코딩하여 ΔG(cf) - ΔG(lin)를 분류하는 기초적인 머신러닝 코드를 제공합니다.

## 프로젝트 구조
```
code/
├── 
└── ΔG_group_prediction.ipynb   # DNA Sequences 인코딩 및 machine learning code
data/
├── dataset-palindrome.csv      # 원본 데이터 파일(Sequences 열에 스페이스바 제거)
├── encoded_sequences.npy       # 시퀀스 인코딩 파일
└── palindrome_with_group       # 원본 데이터에서 ΔG_abs_diff와 ΔG_group 열 추가
```

## 프로젝트 구성

### 데이터셋
- Sequences와 ΔG(cf) - ΔG(lin)를 포함한 12개의 열과 310개의 행으로 이루어진 데이터셋

### 데이터 전처리
- ΔG(cf) - ΔG(lin):
  1. 결측치 제거
  2. ΔG_abs_diff: ΔG(cf)와 ΔG(lin) 차이 계산 후 절대값 처리
  3. ΔG_group: ΔG_abs_diff을 그룹화
- Sequences:
  1. 결측치 제거
  2. 줄바꿈 문자와 염기서열 소문자를 대문자로 변환
  3. Encoding 및 제로 패딩 적용

### 모델 개발
- Random Forest 모델 사용
  - 기본 파라미터만 사용
  - 평가지표: Accuracy
