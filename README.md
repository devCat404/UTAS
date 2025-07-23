# 멸종위기종 새소리 기반 통합 생태 분석 및 보호정책 제안

## 1. 개요

본 보고서는 희귀 조류의 지저귐 패턴(chattering, screech 등)을 기반으로,  
기후 변화, 서식지 이동, 도심 개발 등의 외부 요인이 멸종위기종에 미치는 영향을 통합적으로 분석하고,  
이를 기반으로 정책, 공원 개발, 생태 보호 전략으로 확장할 수 있는 프레임워크를 제안한다.

---

## 2. 분석 목표

- 희귀한 조류의 지저귐 패턴을 시공간적으로 매핑
- GAN 기반 복원 및 감성 분석을 통해 생태적 상태 해석
- 도시/산업/관광 등의 인적 요소와의 연계성 분석
- 멸종위기종 보호를 위한 실질적 정책 도출

---

## 3. 분석 흐름

<p align="center">
[오디오 녹음 + 위치 데이터]<br>
↓<br>
[지저귐 패턴 분류 (Chattering / Screech)]<br>
↓<br>
[GAN 복원 및 데이터 증강]<br>
↓<br>
[감성 분석: 평온 / 경계 / 스트레스]<br>
↓<br>
[시계열 및 위치 기반 서식지 매핑]<br>
↓<br>
[도심/공업지/관광지 등과 중첩 분석]<br>
↓<br>
[정책·개발 방향성 제안]
</p>

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="https://tse3.mm.bing.net/th/id/OIP.QSQVK9XLv8hQSm5LnHScsAHaHF?w=400&h=400" alt="Mel Spectrogram Bird" width="250"/><br>
        <sub>Mel Spectrogram</sub>
      </td>
      <td align="center">
        <img src="https://tse2.mm.bing.net/th/id/OIP.8TxHieOXtdTvWUpmI_sS7AHaEW?w=400&h=400" alt="Spectrogram with features" width="250"/><br>
        <sub>Feature Spectrogram</sub>
      </td>
    </tr>
    <tr>
      <td align="center">
        <img src="https://tse1.mm.bing.net/th/id/OIP.3TLGIbpQxLx1ou1tdtUorgHaGE?w=400&h=400" alt="Waveform and Spectrogram" width="250"/><br>
        <sub>Waveform & Mel</sub>
      </td>
      <td align="center">
        <img src="https://tse1.mm.bing.net/th/id/OIP.ciDAXYofWTfW1jf7Jq7rxgHaGD?w=400&h=400" alt="American Crow Spectrogram" width="250"/><br>
        <sub>Spectrogram</sub>
      </td>
    </tr>
  </table>
</div>



---

## 4. 분석 요소별 세부 내용

### 4.1 지저귐 패턴 기반 행동 해석

| 패턴      | 생태적 의미                         |
|-----------|--------------------------------------|
| Chattering | 사회적 유대, 번식기 진입 신호       |
| Screech    | 위협 반응, 스트레스 지표             |

- 특정 시점에 chattering이 집중 → 번식기 또는 활동기 가능성
- screech 비율이 증가 → 환경 교란 또는 포식자 스트레스


---

### 4.2 GAN 기반 복원 및 데이터 증강

- 희귀종의 희미한 소리 복원
- 소량 샘플을 기반으로 한 데이터 증강
- 장기 모니터링에 필요한 안정적 입력 확보

---

### 4.3 감성 분석 및 생태 스트레스 탐지

- 정서 분류: 평온 / 경계 / 스트레스
- 이상 패턴 탐지 → 환경 변화 조기 경고 시스템 가능



<div align="center">
  <table>
    <tr>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/63945ace-4690-45a5-8b84-7587d39069f7" /><br>
      </td>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/9c90cf1f-868b-49f9-bc3f-446e357b63b9" /><br>
      </td>
    </tr>
  </table>
</div>
---

### 4.4 시공간 기반 서식지 변화 매핑

- 오디오 + 위치 + 시간 데이터 기반 시계열 분석
- 특정 종의 서식지 변화, 이주 경로, 활동 시간대 시각화

<pre lang="python">
  import matplotlib.pyplot as plt 
  import numpy as np 
  
  # Sample habitat coordinates (latitude, longitude) 
  locations = { 
    "Tasmania": (-42.8821, 147.3272), 
    "Mainland Australia": (-25.2744, 133.7751), 
    "New Zealand": (-40.9006, 174.8860), 
    "SE Asia": (5.354, 100.298) 
  } 
  
  # Separate latitudes and longitudes 
  lats = [loc[0] for loc in locations.values()] 
  lons = [loc[1] for loc in locations.values()] 
  
  names = list(locations.keys())
  
  # Visualization 
  plt.figure(figsize=(10, 6))
  plt.scatter(lons, lats, s=200, c='green', alpha=0.7, edgecolors='black') 
  
  # Add labels 
  for i, name in enumerate(names): 
    plt.text(lons[i] + 0.5, lats[i], name, fontsize=12) 
    plt.title("Sample Bird Habitat & Migration Nodes") 
    plt.xlabel("Longitude") plt.ylabel("Latitude") 
    plt.grid(True) 
    plt.tight_layout() 
    plt.show() </pre>

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/8182ed95-c463-4ebe-a2b4-63d2e5f9c10f" /><br>
        <sub>Habitat Heatmap (Cornell NBHCI)</sub>
      </td>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/a317d0d9-c248-444c-b435-9ea64180584a" /><br>
        <sub>Bird Migration Routes</sub>
      </td>
    </tr>
    <tr>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/ff69a5c0-4da5-4605-9087-da049aec1202" /><br>
        <sub>Boreal Migration Patterns</sub>
      </td>
      <td align="center">
        <img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/ca639dec-8d5d-4193-8023-27d403cf6cd7" /><br>
        <sub>Stopover Habitat: Lake Erie</sub>
      </td>
    </tr>
  </table>
</div>

---

### 4.5 정책 및 생태 보호 전략 적용

#### 🔍 정책 적용 시 고려 사항

- **도입 시기 결정**: chattering 패턴이 활성화되는 시기를 기준으로 보호구역 확대 또는 출입 통제
- **공원 개발 및 관광 허용 시간 설정**: 새들의 활동 저해가 최소화되는 시간대에만 개방
- **서식지 특성화 시간대 파악**: 특정 시간에 종별 활성도가 집중되는 경우, 해당 시간대를 보호 구간으로 설정
- **산업/공업지역 개발 제한**: screech 비율 증가 또는 서식지 이탈이 감지될 경우 개발 지연 또는 보완 조치 도입
- **실시간 오디오 모니터링 시스템 구축**: 일정 지역에 정기 녹음 장치 설치 → 주기적으로 패턴 분석 및 알림 시스템 운영

#### 🗺 보호 및 정책 연계

- **서식지 맵 기반 보호구역 설정**
- **지역 감성 분석 결과에 기반한 정책 우선순위 조정**
- **이주 가능성 높은 지역에 대한 조기 탐지 및 대응**

---

## 5. 기대 효과

- 생물 다양성 보전과 기후변화 대응 전략의 정교화
- 보호 정책의 과학적 타당성 확보
- 생태 관광과 도시 계획의 균형 있는 조정
- 멸종위기종 보호와 공공 정책의 연계 기반 마련

---

## 6. 확장 가능성

- 다른 포유류/양서류 소리 데이터와 통합
- 드론 기반 위치 추적 및 실시간 데이터 수집
- 시계열 기반 서식지 AI 예측 시스템 구축
