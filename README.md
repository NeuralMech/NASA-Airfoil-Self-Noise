# NASA Airfoil Self-Noise Analysis

NASA Airfoil Self-Noise Dataset을 이용해 익형 자체 소음(Self-Noise)을 분석한 개인 학습 프로젝트입니다.

이 저장소는 공력소음 데이터를 대상으로 주파수, 유속, 받음각, 코드 길이, 변위 두께 등의 변수와 음압 수준(Sound Pressure Level) 사이의 관계를 탐색하고, 기본적인 회귀 모델을 통해 예측 가능성을 확인하기 위해 만들었습니다.

## Motivation

기계공학 및 항공·유체 시스템에서는 진동, 소음, 유동 조건이 시스템 성능과 안정성에 직접적인 영향을 줍니다. 특히 공력소음은 단순한 구조 문제나 유동 문제만으로 분리하기 어렵고, 실험 데이터 기반 분석과 물리적 해석을 함께 고려해야 하는 주제입니다.

이 프로젝트에서는 공개 데이터셋을 활용해 공력소음 데이터의 변수 구조를 이해하고, 주파수 대역별 특성과 회귀 모델의 예측 성능을 확인하는 데 초점을 두었습니다. 향후 진동·소음 기반 상태 진단, PHM(Prognostics and Health Management), 물리 기반 머신러닝 연구로 확장하기 위한 기초 분석입니다.

## Dataset

사용한 데이터셋은 NASA Airfoil Self-Noise Dataset입니다.

데이터는 익형 주위 유동 조건과 그에 따른 소음 수준을 포함합니다.

**주요 변수**

- Frequency
- Angle of attack
- Chord length
- Free-stream velocity
- Suction side displacement thickness
- Scaled sound pressure level

본 프로젝트에서는 특히 `frequency`를 단순 설계변수라기보다 소음 스펙트럼을 해석하기 위한 축으로 보고 분석했습니다.

## Current Contents

- `AirfoilSelfNoise.ipynb`  
  NASA Airfoil Self-Noise Dataset 분석 노트북입니다.
  - 데이터 구조 확인
  - 변수 간 상관관계 분석
  - 주파수 대역별 소음 특성 정리
  - 유속, 받음각, 코드 길이 등에 따른 SPL 변화 확인
  - 선형 회귀 및 Random Forest 기반 예측 모델 비교
  - 결과 해석 및 한계 정리

- `Airfoil Self-Noise.pdf`  
  분석 과정과 주요 결과를 정리한 문서입니다.

## Analysis Focus

이 프로젝트에서 중점적으로 확인한 부분은 다음과 같습니다.

1. 공력소음 데이터에서 각 입력 변수가 SPL에 어떤 영향을 주는지
2. 주파수 대역별로 소음 특성이 어떻게 달라지는지
3. 유속, 받음각, 코드 길이 등 물리적 변수와 소음 수준 사이의 관계
4. 단순 선형 모델과 비선형 회귀 모델의 예측 차이
5. 데이터 기반 분석을 기계·유체 시스템 해석과 어떻게 연결할 수 있는지

## Methods

사용한 주요 분석 방법은 다음과 같습니다.

- Exploratory Data Analysis
- Correlation Analysis
- Frequency-band Analysis
- Data Visualization
- Linear Regression
- Random Forest Regression
- Model Performance Comparison

## How to Run

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook AirfoilSelfNoise.ipynb
```

## Limitations

이 프로젝트는 공력소음에 대한 완전한 물리 모델을 구축한 것이 아니라, 공개 데이터셋을 이용한 탐색적 분석과 기본적인 회귀 모델 비교에 가깝습니다.

특히 다음과 같은 한계가 있습니다.

- 원본 데이터가 이미 주파수별 측정값으로 정리되어 있어, 시간 신호에 대한 FFT 분석은 수행하지 못했습니다.
- 데이터 기반 회귀 모델의 예측 성능은 확인했지만, 물리 기반 모델이나 PINN 구조와 직접 연결하지는 못했습니다.
- 향후에는 실제 진동/소음 시계열 데이터에서 주파수 분석을 수행하고, 이를 고장 진단 또는 PHM 문제와 연결해 보고자 합니다.

## Planned Extensions

- NASA Bearing Dataset 등 진동 기반 PHM 데이터셋 분석
- FFT 기반 주파수 영역 특징 추출
- 소음·진동 데이터의 상태 진단 문제 적용
- 회귀 모델 외의 딥러닝 기반 예측 모델 비교
- 물리 기반 머신러닝 또는 PINN과의 연결 가능성 검토

## Reference

- NASA Technical Report: Airfoil Self-Noise Dataset  
  https://ntrs.nasa.gov/api/citations/19890016302/downloads/19890016302.pdf

## Note

이 저장소는 개인 학습 및 연구 준비를 위한 프로젝트입니다. 공력소음 데이터의 구조를 이해하고, 기계 시스템의 소음·진동 분석을 데이터 기반 방법과 연결하기 위한 기초 분석으로 정리하고 있습니다.
