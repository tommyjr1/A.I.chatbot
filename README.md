# AI(아직 인간이 낫다
madcamp week3

## 팀원 : 금나연, 송재현

## Development Environment

### *Python 3.6.9*

  * OpenJDK version : 11.0.11
  * JPype version : JPype1‑1.1.2‑cp36
  * Konlpy version : v0.5.2.
  * tensorflow version : 2.5.0
  * Flask version : 2.0.1
  * Ubuntu : 18.04.2
  * MySQL version : 5.7.34, for Linux (x86_64)
  * Naver TalkTalk API

## Introduction
- 대화형 챗봇 개발

## Pipeline
### Training
*1. Intent*
- 7개의 문맥(intent)이 라벨링된 105681개의 데이터에서 문장 내 키워드를 추출
    {0: "인사", 1: "욕설", 2: "주문", 3: "예약", 4: "기타", 5:"이별", 6:"사랑"}
- 단어 시퀀스 벡터를 만들어 CNN을 이용해 모델 학습, 평가 및 저장 ('models/intent/intent_model.h5')

*2. Ner*
- 형태소 별로 160458개의 문장을 분석하여 라벨링된 데이터 이용
    B_FOOD : 음식
    B_DT, B_TI : 시간 (학습 데이터의 영향으로 날짜와 시간을 혼용해서 사용)
    B_PS : 사람
    B_OG : 조직, 회사
    B_LC : 지역
- 단어 시퀀스 벡터를 만들어 Bi-LSTM을 이용해 모델 학습, 평가 및 저장 ('models/ner/ner_model.h5')

## 실행 
- Server : bot.py
- Client : chatbot_api/app.py
- Chatbot : https://talk.naver.com/ct/w4gxjf


