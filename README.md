# STARBOX
- 국내 대표 차(Tea) 브랜드 '[오설록](https://www.osulloc.com/kr/ko)'을 모티브로 한 프로젝트입니다.
- 사이트 선정 이유
  -  처음 프로젝트인 만큼 그동안 배운 지식을 활용하여 e-커머스에 crud 기반으로 직접 기능들을 구현해보고 적용해볼 수 있는 사이트를 선정

![오설록](https://user-images.githubusercontent.com/108418225/190359024-709b2df0-3249-4708-8e2f-7d6bcb38c07a.png)

  
  
## 1. 개발 기간 및 인원

- __개발 기간__  : 2022.08.29 ~ 2022.09.08

- __프론트엔드__ : 유상호, 김정연, 이동호, 이유나  

- __백엔드__ : 김교은, 박지은  

- __[프론트엔드 GitHub](https://github.com/wecode-bootcamp-korea/justcode-6-1st-osamloc-front)__ 

- __[팀 노션](https://www.notion.so/wecode/93b4fdf1dd4b49dd9b2fe71f7b85d8d0)__

  
  
## 2. 데이터 모델링

:paperclip:  [dbdiogram 링크](https://dbdiagram.io/d/631550500911f91ba5332730)   

![디비](https://user-images.githubusercontent.com/108418225/190328843-2bbf8125-2c98-43a3-a3d0-f31fd9613631.png)

  
 
## 3. 적용 기술 및 구현 기능

### 3-1. 적용 기술(수정 필요)
+ Front-end : React.js(개발환경은 CRU), sass, fetch, webpack(컴파일러는  babel)
+ Common : RESTful API
+ Community Tools : Slack, Zoom, Notion, Zepp
+ Version Control Tool : Git(flow는 github flow방식을 따름)


### 3-2. 프론트엔드 구현 기능

>프론트엔드  
  
- 이동호  
  - [장바구니] UI
  - [장바구니] 리스트 CRUD 기능 구현 
  - [장바구니] 금액 합산 기능 추가
  - [결제페이지] UI
  - [결제페이지] 정규식 검증
  - [결제페이지] 주소API 연동
  - [결제페이지] 결제API 연동
  - [장바구니] 데이터 통신
  - [결제페이지] 데이터 통신

- 유상호
  - [베스트 페이지] markup
  - [제품 페이지] markup
  - [제품 페이지] 최상단 카테고리 기능 추가
  - [제품 페이지] 제품별 카테고리 기능 추가
  - [제품 페이지] pagination 기능 추가
  - [제품상세페이지] ui&기능

- 김정연
  - [메인 페이지] 전체 UI
  - [메인 페이지] CardSection UI
  - [메인 페이지] 다다일상 구독 Hover, animation
  - [메인 페이지] 다다일상 기록 mock data
  - [메인 페이지] main slide
  - [메인 페이지] 다다일상 기록 slide
  - [메인 페이지] BestSection slide
  - Header UI
  - Header hover
  - [메인 페이지] CardSection 남은시간 계산 기능
  - [메인 페이지] 공지사항 세로 slide 
  - [메인 페이지] BestSection filter

- 이유나
  - [로그인/회원가입] UI
  - [회원가입 페이지] input 조건문 /알림설정
  - [체크박스] 전체선택/ 일부선택기능
  - [로그인 페이지] input 클릭시 조건문 알람
  - [로그인 페이지] input 클릭시 테두리 색변화 
  - footer ui&기능 
  
>백엔드

- 김교은  
  - 카테고리 API  
  - 상품 리스트 API  
  - 상품 정렬 API  
  - 장바구니 / 결제 API  

- 박지은
  - 회원가입 / 로그인 API 
  - 상품 상세 페이지 API   
  - 리뷰 API

  
## 4. 내가 구현한 페이지

### 4-1. 장바구니 페이지
- 먼저 사용자의 가시성을 높이기 위해서 체크박스 상호작용에 중점을 두었다. 
전체선택부분 체크박스를 클릭하게되면 전체선택, 전체해제가 가능해지며, 전체해제를 하고 상품 하나하나의 체크박스를 다 체크해도 전체선택부분 체크박스가 자동으로 체크표시 되게 해놓았다. 
원리는 상위 컴포넌트에서 useState로 체크박스 전체에 대한 상태를 설정하고 하위 컴포넌트들이 모두 공유할 수 있도록 해놓았다.
그리고 선택 상품결제, 전체 상품결제 두가지를 만들어서 위에서 useState로 관리한 체크박스 전체 상태를 통해서 선택 상품결제는 체크박스 상태를 같이 결제 페이지로 보내주도록 구현했다.

![장바구니gif형태](https://user-images.githubusercontent.com/88419431/190587405-01e87431-6180-4967-bc8b-64024fb5ed25.gif)

### 4-2. 결제 페이지
- 외부api를 통해 정보를 받아오고 백엔드의 전달하는 것에 중점을 두었다.
외부 api는 두가지를 사용했고, 먼저 주소api는 상용자의 편의를 위해서 사용했고 다음에서 제공하는 주소찾기오픈api를 이용했다.
기본 주소를 모달창에 입력하면 우편번호 정보를 자동으로 가져오게 해주는 시스템이다.
두번째는 결제api다. 실제 배포에 중점을 두고 구현을 했기에 완성도를 높이기 위해서 실제처럼 모달창을 띄우고 테스트 결제가 되도록 했다. iamport에서 제공하는 오픈api를 사용했고, 결제수단은 사용자의 편의를 위해서 4가지로 구성했다.  

![결제페이지gif형태](https://user-images.githubusercontent.com/88419431/190586976-fc7a7e6e-c74d-4d48-8757-e04fc72c4c45.gif)





  
  
## 5. API Docs

:paperclip: [회원가입 / 로그인 / 상품 상세 페이지 / 리뷰 API](https://documenter.getpostman.com/view/22723173/VUxVrQLd)  
:paperclip: [카테고리 / 상품 필터, 정렬 / 상품 리스트 API](https://documenter.getpostman.com/view/22723465/VUxXKNsa)  
:paperclip: [장바구니 / 결제 API](https://documenter.getpostman.com/view/22723465/VVBQX98b)  

## Reference

- 이 프로젝트는 [오설록](https://www.osulloc.com/kr/ko) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.


