## 국내 여행지 추천 프로젝트
주제 : Sentence Transformer를 활용한 사용자의 입력에 따른 여행지 추천 모델 구현 및 LangChain 및 Streamlit을 이용한 여행지 추천 챗봇 구현

기간 : 2024.09.12 ~ 2024.10.07

인원 : 4명 (배누리, 박현아, 정기현, 안준영)

<br>

## 프로젝트 소개
### 1. Sentence Transformer를 활용한 사용자의 입력에 따른 여행지 추천 모델 구현
  <img width="697" alt="Image" src="https://github.com/user-attachments/assets/5e4d8fdd-a515-4885-a7f6-9567d20e98fa" />

  1. 데이터 및 전처리 
  - Tour API 4.0 에서 제공하는 관광지 데이터를 사용
  - 각 데이터에서 필요한 열만 추출 후 분류를 위해 대분류와 중분류 열을 추가로 생성 (대분류 : 축제, 문화시설, 관광지, 쇼핑, 음식점 등 | 중분류 : (예:축제의 중분류) 전통공연, 전시회, 연극 등

  2. 임베딩 생성
  - 각 열별로 Sentence Transformer 모델을 사용하여 각 열별 임베딩 생성
  
  3. 사용자 입력에 따른 답변 생성
  - 사용자가 입력한 텍스트를 임베딩 벡터로 변환하여 이전에 생성한 임베딩 열에 대한 코사인 유사도를 계산
  - 각 유사도에 대한 가중치를 부여하여 총합 유사도를 계산한 후 상위 5개에 대한 관광지를 추출하고 각 관광지에 대한 요약을 출력
  - 관광지에서 열리는 축제와 folium을 사용하여 구글 맵에 5개의 관광지 위치를 마커로 표시하여 출력


### 2. LangChain 및 Streamlit을 이용한 여행지 추천 챗봇 구현
  <img width="791" alt="Image" src="https://github.com/user-attachments/assets/fdbb1074-a874-4256-81a9-d8bc91bf2173" />
  
  1. LangChain
  - Sentence Transformer를 활용한 사용자의 입력에 따른 여행지 추천 모델과의 비교를 위해 OpenAI의 GPT-4.0 모델을 사용하여 챗봇을 구현함
  - Streamlit을 활용하여 프롬프트를 수정 기능을 제공하였고 대화 내용을 저장하여 AI가 이전의 대화 내용을 참고하도록함
  - 관광지 위치를 표시하기 위해 Google Maps Geocoding API를 사용해 관광지 이름을 좌표로 변환하고 Folium을 사용해 지도에 마커로 표시하여 출력



