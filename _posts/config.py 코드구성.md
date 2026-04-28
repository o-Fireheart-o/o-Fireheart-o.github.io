---
title: "config.py 코드구성"
date: "2026-04-29 00:14 +0900"
categories: [Category]
tags: [tag]
layout: post
---
## 활용 라이브러리
`os` `dotenv`
## 라이브러리 불러오기
```python
import os
from dotenv import load_dotenv

# .env 파일의 내용을 운영체제 환경 변수로 로드
load_dotenv()
```

## client_id, client_secret 
```python
# APS 인증정보 가져오기
CLIENT_ID = os.getenv("APS_CLIENT_ID")
CLIENT_SECRET = os.getenv("APS_CLIENT_SECRET")

# 환경변수에서 bucket 찾고 없으면 생성하기
APS_BUCKET = os.getenv("APS_BUCKET", f"{CLIENT_ID}-basic-app")
# 포트 설정 (환경변수에 PORT가 없으면 기본값 8080 사용하기)
PORT = int(os.getenv("PORT", 8080))
```
## 필수 환경 변수 누락 처리
```python
if not client_id or not client_secret:
	print("Missing required environment variables.")
	exit(1)
```
---
## 💡추가 내용
### 표준 라이브러리 (Standard Library)
- 출신 : 파이썬을 설치할 때 기본적으로 포함되어있는 라이브러리
- 특징 : 별도로 터미널에서 `pip install`을 통해 설치할 필요가 없음
- 예시 : `import os` `import math`...
### 외부 라이브러리(Third-Party Library)
- 출신 : 다른 개발자들이 만들어서 배포한 외부 라이브러리
- 특징 : 사용하려면 반드시 터미널에서 `pip install`을 통해 설치해야함
- 예시 : `dotenv` `requests`...
### 프레임워크와 라이브러리의 차이
- 주도권이 누구에게 있는가에 차이가 있음
- 라이브러리 : 내가 필요할때 꺼내 쓰는 도구 (주도권이 나한테 있음)
- 프레임워크 : 나를 규칙안에 가두고 동작함 (프레임워크가 주도함)