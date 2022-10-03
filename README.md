# STARBOX
- 국내 대표 영화 티켓팅 사이트 '[메가박스](https://www.megabox.co.kr/)'을 모티브로 한 프로젝트입니다.
- 사이트 선정 이유
  -  처음 프로젝트를 E-COMMERCE로 하였기에, 새로운 분야와 해당 페이지들을 가진 티켓팅 사이트를 하게 되었다.

![메가박스](https://user-images.githubusercontent.com/108418225/190359024-709b2df0-3249-4708-8e2f-7d6bcb38c07a.png)

  
  
## 1. 개발 기간 및 인원

- __개발 기간__  : 2022.09.19 ~ 2022.09.30

- __프론트엔드__ : 이동호, 김정연, 박유빈, 양미옥

- __백엔드__ : 김민우, 오인환

- __[프론트엔드 GitHub](https://github.com/wecode-bootcamp-korea/justcode-6-2nd-team2-front)__ 

- __[팀 노션](https://github.com/wecode-bootcamp-korea/justcode-6-2nd-team2-back)__

  
  
## 2. 데이터 모델링

:paperclip:  [dbdiogram 링크](https://dbdiagram.io/d/6327c6e10911f91ba5db0917)   

![디비](https://user-images.githubusercontent.com/108418225/190328843-2bbf8125-2c98-43a3-a3d0-f31fd9613631.png)

  
 
## 3. 적용 기술 및 구현 기능

### 3-1. 적용 기술(수정 필요)
+ Front-end : React.js(개발환경은 CRU), sass,styled-componets, fetch,axios,,ContextAPI,webpack(컴파일러는  babel)
+ Common : RESTful API, PostMan, LiveServer
+ Community Tools : Slack, Zoom, Notion, Zepp, Trello
+ Version Control Tool : Git(flow는 github flow방식을 따름)


### 3-2. 프론트엔드 구현 기능

>프론트엔드  
  
- 이동호  
  - [예매페이지] 빠른예매 화면 UI 및 레이아웃
  - [예매페이지] 날짜, 시간별 슬라이드 추가
  - [예매페이지] 더보기 달력 추가 및 에러 헨들링 모달 기능
  - [예매페이지] 좌석선택 화면 전체 UI
  - [예매페이지] 인원별 좌선 선택 기능
  - [예매페이지] 결제화면 전체 UI
  - [예매페이지] 결제API 연동
  - [상영시간표] 전체 UI 및 레이아웃
  - [상영시간표] 더보기 달력 추가
  - [상영시간표] 날짜별 슬라이드
  - [상영시간표] 네비게이션 영화, 극장별 Tab

- 김정연
  - [상세페이지] 전체 레이아웃 잡기
  - [상세페이지] 누적관객수 tooltip
  - [상세페이지] 기대평 등록 삭제 레이아웃
  - [상세페이지] 무비포스트 레이아웃
  - [상세페이지] 예고편 레이아웃
  - [상세페이지] 스틸컷 레이아웃
  - [상세페이지] 기대평 map
  - [상세페이지] 예매버튼 링크
  - [상세페이지] 좋아요 api

- 박유빈
  - [영화리스트] 전체 UI
  - [영화리스트] 영화 카테고리 페이지 이동 기능
  - [영화리스트] 박스오피스 레이아웃
  - [영화리스트] 영화 리스트 카운트 기능
  - [영화리스트] 영화 리스트 map
  - [영화리스트] 영화 더보기 페이지네이션 기능
  - [영화리스트] 영화 포스트 이벤트
  - [영화리스트] 영화 검색 기능
  - [영화리스트] 영화 필터 기능

- 양미옥
  - [헤더] UI
  - [헤더] use의 이동경로에 따른 ui 구현
  - [헤더] 서브메뉴 탭기능
  - [로그인] UI
  - [로그인] 휴대폰 인증 기능
  - [로그인] 약관동의 레이아웃
  - [로그인] 약관동의 필터 기능
  
>백엔드

- 김민우  
  - 영화 리스트조회 API
  - 영화 상세페이지 조회 API 
  - 상영스케쥴 조회 API
  - 좌석선택 API
  - 티켓생성 API
  - 영화 좋아요 추가/삭제 API  

- 
  - 회원가입 / 로그인 API 
  - 로그인시 토큰 인증/인가 API   
  - 마이페이지 API

  
## 4. 내가 구현한 페이지

### 4-1. 예매 페이지
- 먼저 예매페이지 첫화면에서는 먼저 레이아웃을 잡는데 꽤 고생을 했고 가장 키포인트였다. 중점을 둔 부분은 슬라이드였다. 날짜를 화살표버튼을 누르면 넘어가게 하는 형태로 구성했으며, react-swiper라는 라이브러리를 통해 구현하였고, date-picker로 구현한 달력에서도 날짜를 구현하면 슬라이드에서 해당날짜로 이동하게 구현하였다. 이외에는 3개 이상 선택을 할 경우 분기점을 두고, 모달로 막아두었고 시간표에도 슬라이드를 구성하여 해당 시간대를 클릭하면, 해당 시간대 이후에 상영시간만 나오도록 프론트에서 자체적으로 filter를 구성하였다. 
두번째 화면에서는 좌석선택시 효과에 대해 중점을 두고 구현하였다. onMouseOver, onMouseLeave로 hover효과를 주었고 좌석 지정상태를 useState로 관리하여 오른쪽 결과창에 반영되도록 하였다.
마지막 세번째 화면에서는 실제로 결제 하는 부분으로서 iamport라는 외부 결제 라이브러리를 연동하여 카카오페이로 결제가 가능하도록 구현했다.
그리고 모든 컴포넌트에서 예매정보에 대해서 상태를 공유할 수 있도록 context로 관리하였다.

![장바구니gif형태](https://user-images.githubusercontent.com/88419431/190587405-01e87431-6180-4967-bc8b-64024fb5ed25.gif)

### 4-2. 상영시간표 페이지
- 위에 예매페이지와 겹치는 UI가 많았기에 비교적 수훨하였고 제일 중점을 두었던 부분은 백엔드에서 시간순서로 준 상영표를 관별로, 지역별로 다시 sort하여 구현하는 것이었다.
먼저 위에 네비게이션 박스는 받는 props로 렌더링되는 컴포넌트를 구분하였다. 또한 슬라이드는 동일하게 react-swiper를 사용하고, 실제 시간표를 hover하였을때, 영상시간과 현재 남은 좌석을 표시하고 클릭하면 해당 영화시간에 좌석페이지로 이동할 수 있도록 구현하였다. 
다음으로 관별, 지역별로 sort하여 표시해주는 것은 백엔드에서 받은 데이터를 filter와 foreach함수를 통하여 다시 순서를 맞추고 map을 돌렸다. 

![결제페이지gif형태](https://user-images.githubusercontent.com/88419431/190586976-fc7a7e6e-c74d-4d48-8757-e04fc72c4c45.gif)





  
  
## 5. API Docs

:paperclip: [회원가입 / 로그인 / 상품 상세 페이지 / 리뷰 API](https://documenter.getpostman.com/view/22723173/VUxVrQLd)  
:paperclip: [카테고리 / 상품 필터, 정렬 / 상품 리스트 API](https://documenter.getpostman.com/view/22723465/VUxXKNsa)  
:paperclip: [장바구니 / 결제 API](https://documenter.getpostman.com/view/22723465/VVBQX98b)  

## Reference

- 이 프로젝트는 [오설록](https://www.osulloc.com/kr/ko) 사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.


