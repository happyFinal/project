![header](https://capsule-render.vercel.app/api?type=waving&color=6FC7E1&height=130&section=header&fontSize=35)
<header> 
<h1> ✍️ 삼행시 ai 프로젝트 </h1>
</header>

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FhappyFinal%2Fproject&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=visits&edge_flat=false)](https://hits.seeyoufarm.com)

<br>

## ✅ 프로젝트 개요

멋쟁이 사자처럼 AI스쿨 부트캠프 7기의 수료과정 중 파이널 프로젝트로 시작하게 되었습니다.

자연어 처리 분야에서 텍스트 데이터 전처리 및 생성 태스크의 이해도를 높이고, 허깅페이스의 모델 활용을 실습해보고자 해당 주제를 선택하였습니다.

멜론 발라드 장르 최신곡을 인기순으로 정렬하여 크롤링한 후, KoGPT2에 텍스트 생성 태스크를 할당하여 삼행시를 만들어주는 ai를 제작하였습니다.



## ✅ Stack

#### 데이터 전처리
<img src="https://img.shields.io/badge/Numpy-013243?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"> 
<img src="https://img.shields.io/badge/KonlPy-ED1C24?style=for-the-badge&logo=Python&logoColor=white"> 

#### 데이터 시각화



#### 모델링
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">  <img src="https://img.shields.io/badge/Google Colab-F9AB00?style=for-the-badge&logo=google colab&logoColor=white"> <img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white"> <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white">

#### 배포
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white">

#### 🔗 배포링크 1 - streamlit webapp: https://happyfinal-streamlit-main-cjyf11.streamlit.app/

#### 🔗 배포링크 2 - huggingface: https://huggingface.co/spaces/dk-davidekim/happyFinal-Streamlit


<br>


## ✅ 생성 예시

[배포 사이트 캡처본 추가 예정]


<br>



## ✅ 데이터셋

1️⃣ 텍스트 전처리

- 크롤링한 데이터를 .csv 확장자로 저장한 후, 개행문자 '\n'을 포함하지 않은 데이터를 제거하였다.
- 데이터에 한글, 숫자, 개행문자만을 남겼는데, 숫자를 남긴 이유는 '1번', '3일' 등의 단어를 한글 수사로 매핑하지 않고 바로 사용하기 위해서이다.
- 공백이 2회 이상 반복될 경우에도 제거해주고, 전처리 후 빈 행이나 10자 이상 안 되는 행 또한 제거하였다.
- 전처리 완료 후에는 인덱스를 초기화해주고, 개행 문자를 기준으로 리스트로 만들어 활용하거나 split하여 .txt 확장자 파일로 만들어 모델을 학습시켰다.

2️⃣ 음악 장르별 EDA (Exploratory Data Analysis)

- 힙합, 댄스, RNB 장르는 영어의 비율이 높게 나타났다. → 토큰화 과정에서 KonlPy 라이브러리를 활용하기 위해 영단어 배제.
- 힙합 vs 발라드의 영문 가사 비교 시각화
- 댄스 vs 발라드의 영문 가사 비교 시각화

- 인디는 장르 특성상 주제가 다양했다 → 주제가 다양한 만큼 문장 생성 시 맥락에 맞지 않는 구 혹은 문장이 생성될 위험 배제
- 트로트 장르는 무의미한 추임새의 반복이 많았다 → 
- 예시: 진진자라
진진자라 지리지리자
진진자라 지리지리자
진진자라 지리지리자
바람처럼 왔다가
불꽃처럼 사랑하고
구름처럼 흘러가는
진진자라 지리지리자
진진자라 지리지리자
진진자라 지리지리자



3️⃣ 




## ✅ 프로젝트 팀원


<table>
<tr>
<th> 지혜 </th>
<th> 종현 </th>
<th> 의준 </th>
<th> 자현 </th>
<th> 지영 </th>
<th> 소희 </th>
  </tr>
  
  
  
<td><a href = "https://github.com/eveoreveline">
  <img src="https://user-images.githubusercontent.com/99390776/210307070-7215a15f-dff4-4dc6-82a2-dfd50dd7b18c.png" width = '80%'/> </a> </td>
<td><a href = "https://github.com/moonstar97">
  <img src="https://user-images.githubusercontent.com/99390776/210307034-97f2af95-de13-4d3a-b3d7-f9c4ca6f50d4.png" width ='80%'/> </a> </td>
<td><a href = "https://github.com/dk-davidekim">
  <img src="https://user-images.githubusercontent.com/99390776/210307359-b22d1e72-41d1-41a8-9ce0-9caae342805c.png" width ='80%'/> </a> </td>
<td><a href = "https://github.com/wumusill">
  <img src="https://user-images.githubusercontent.com/99390776/210307346-43055bce-4a30-442a-93a0-f770ceb5e914.png" width ='80%'/> </a> </td>
<td><a href = "https://github.com/Jiyoeng">
  <img src="https://user-images.githubusercontent.com/99390776/210307368-3f5886aa-e65e-4824-bff8-515466393ab1.png" width ='80%'/> </a> </td>
<td><a href = "https://github.com/qualified-user">
  <img src="https://user-images.githubusercontent.com/99390776/210307381-098cafcd-b96f-4b2c-b219-b178032f5ede.png" width ='80%'/> </a> </td>
</table>

<br>
