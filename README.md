![header](https://capsule-render.vercel.app/api?type=waving&color=6FC7E1&height=130&section=header&fontSize=35)
<header> 
<h1> ✍️ 삼행시 ai 프로젝트 </h1>
</header>

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FhappyFinal%2Fproject&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=visits&edge_flat=false)](https://hits.seeyoufarm.com)

<br>

## ✅ 프로젝트 개요

멋쟁이 사자처럼 AI스쿨 부트캠프 7기의 수료과정 중 파이널 프로젝트로 시작하게 되었습니다. 자연어 처리 분야에서 텍스트 데이터 전처리 및 생성 태스크의 이해도를 높이고, 허깅페이스의 모델 활용을 실습해보고자 해당 주제를 선택하였습니다. 멜론 발라드 장르 최신곡을 인기순으로 정렬하여 크롤링한 후, KoGPT2에 텍스트 생성 태스크를 할당하여 삼행시를 만들어주는 ai를 제작하였습니다.

<br>

## ✅ Stack

#### 웹 크롤링

<img src="https://img.shields.io/badge/Beautiful Soup4-00A98F?style=for-the-badge&logo=Python&logoColor=white"> <img src="https://img.shields.io/badge/Selenium-ECD53F?style=for-the-badge&logo=Python&logoColor=black">


#### 데이터 전처리
<img src="https://img.shields.io/badge/Numpy-013243?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"> 
<img src="https://img.shields.io/badge/KonlPy-ED1C24?style=for-the-badge&logo=Python&logoColor=white"> 

#### 데이터 시각화

<img src="https://img.shields.io/badge/Seaborn-31A8FF?style=for-the-badge&logo=Python&logoColor=white"> <img src="https://img.shields.io/badge/Matplotlib-FF4F8B?style=for-the-badge&logo=Python&logoColor=white">


#### 모델링
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">  <img src="https://img.shields.io/badge/Google Colab-F9AB00?style=for-the-badge&logo=google colab&logoColor=white"> <img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white"> <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white">

#### 배포
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white">

#### 🔗 배포링크 1 - streamlit webapp: https://happyfinal-streamlit-main-cjyf11.streamlit.app/

#### 🔗 배포링크 2 - huggingface: https://huggingface.co/spaces/dk-davidekim/happyFinal-Streamlit


<br>
<br>


## ✅ 생성 예시

[배포 사이트 캡처본 추가 예정]


<br>
<br>


## ✅ 데이터셋

1️⃣ 웹 크롤링

- 중간중간 뜨는 에러 메세지는 웹페이지가 불러와지기 전에 html을 긁으려고 해서 발생하는 문제. → 곡 정보를 불러오는게 딜레이가 없어서 발생한 것으로 유추

```time.sleep() 추가 (driver.implicitly_wait(10) 을 사용해도 에러 해결이 안됨)```

```또는 WebDriverWait() 시간 추가```

- driver.implicitly_wait(10) : 10초안에 웹페이지를 load 하면 바로 넘어가거나, 10초를 기다림

```time.sleep(10) : 10초를 기다림```

- 페이지 하단 인덱스(y)를 돌 때 XPATH 에서 첫번째 페이지 → 세 번째 페이지로 도는 오류 발견함

```css selector로 변경해서 사용하여 해결(첫번째 인덱스 스킵하기 위해 y+1값 사용)```


🔗 웹 크롤러: https://github.com/happyFinal/project/tree/main/crawling


<br>

2️⃣ 텍스트 전처리

- 크롤링한 데이터를 .csv 확장자로 저장한 후, 개행문자 '\n'을 포함하지 않은 데이터를 제거하였다.
- 데이터에 한글, 숫자, 개행문자만을 남겼는데, 숫자를 남긴 이유는 '1번', '3일' 등의 단어를 한글 수사로 매핑하지 않고 바로 사용하기 위해서이다.
- 공백이 2회 이상 반복될 경우에도 제거해주고, 전처리 후 빈 행이나 10자 이상 안 되는 행 또한 제거하였다.
- 전처리 완료 후에는 인덱스를 초기화해주고, 개행 문자를 기준으로 리스트로 만들어 활용하거나 split하여 .txt 확장자 파일로 만들어 모델을 학습시켰다.

<br>

3️⃣ 음악 장르별 EDA (Exploratory Data Analysis)

- 힙합, 댄스, RNB 장르는 영어의 비율이 높게 나타났다. → 토큰화 과정에서 KonlPy 라이브러리를 활용하기 위해 영문가사는 삭제.
- 힙합 vs 발라드의 영문 가사 비교 시각화

![Screenshot 2023-01-03 at 5 26 41 PM](https://user-images.githubusercontent.com/99390776/210321953-e77a91d5-c7fd-4c1f-9101-72cb9feec09d.png)

![Screenshot 2023-01-03 at 5 26 56 PM](https://user-images.githubusercontent.com/99390776/210322000-a0aec509-179d-4a82-8df3-0070add8f674.png)



- 댄스 vs 발라드의 영문 가사 비교 시각화

![Screenshot 2023-01-03 at 5 27 39 PM](https://user-images.githubusercontent.com/99390776/210322093-ca339f99-d70d-465b-847f-3d6f32e623b9.png)


- 인디 장르는 장르 특성상 주제가 다양했다 → 인디장르에서만 등장하는 단어들이 나머지 장르와 섞였을 때 문맥 완성도에 도움을 주지 않을 것으로 판단.
- 트로트 장르는 무의미한 추임새의 반복이 많았다 → 불필요한 단어에 가중치가 할당되어 추임새가 출력되어야 하는 위치에 적절한 단어 토큰이 출력되지 않을 것으로 간주.
- 예시: 진진자라
```
진진자라 지리지리자
진진자라 지리지리자
진진자라 지리지리자
바람처럼 왔다가
불꽃처럼 사랑하고
구름처럼 흘러가는
진진자라 지리지리자
진진자라 지리지리자
진진자라 지리지리자
```

<br>
<br>
<br>

## ✅ 모델링

1️⃣ 토크나이저 관련

```python
tokenizer = PreTrainedTokenizerFast.from_pretrained("skt/kogpt2-base-v2",
                                                    bos_token='</s>', 
																										eos_token='</s>', 
																										unk_token='<unk>',
                                                    pad_token='<pad>', 
																										mask_token='<mask>')

# removed_lines : 전처리된 가사 데이터, 개행 문자 기준 split
tokenized_datasets = tokenizer(removed_lines, # 데이터 형태 아래 사진 첨부 
                               return_tensors="pt", 
                               padding="max_length", 
                               max_length=42,
                               truncation=True)
```

removed_lines : 개행 문자, 영어가 제거된 가사 리스트

<br>

2️⃣ 학습 관련

```python
from transformers import TrainingArguments

# Trainer가 학습, 평가에 사용할 모든 하이퍼 파라미터를 포함하는 클래스 정의
# 학습된 모델이 저장될 디렉토리만 지정하고 나머지는 기본값 사용
training_args = TrainingArguments(
		# 모델 저장 경로
    "/content/drive/MyDrive/Colab Notebooks/ballad_all_model",

		# epoch 설정
    num_train_epochs=10,      
    logging_steps=100000,
    warmup_steps=100000,
    save_steps=100000,
    eval_steps=100000)

###########################################################################
from transformers import EarlyStoppingCallback
from transformers import Trainer

trainer = Trainer(
    model,
    training_args,
    train_dataset=tokenized_datasets,
    eval_dataset=tokenized_datasets,
    tokenizer=tokenizer)
```

🔗 모델: https://github.com/happyFinal/project/tree/main/model

<br>
<br>
<br>

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
  <img src="https://user-images.githubusercontent.com/99390776/210324235-07eb64ba-baf5-4133-847a-80e89c8ee480.png" width ='60%'/> </a> </td>
</table>

<br>
