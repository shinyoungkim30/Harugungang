# HaruGungang 
## 1. 프로젝트 개요
* 과제명 : 건강기능식품정보 및 의약품개요정보 API를 활용한 영양제 정보 제공 반응형 웹서비스
* 프로젝트 기간 : 2023.05.29 ~ 2023.06.27
* 프로젝트 설명 : 영양제를 섭취하거나 섭취하고자 하는 소비자가 필요로하는 (성분, 주의사항, 섭취방법 등)을 직관적이면서도 쉬운 UI로 제공하는 영양제 정보 제공 웹사이트 개발

## 2. 시연영상
https://www.youtube.com/watch?v=mRnVtz-5ddc

## 3. 주요기능
* 간단 설문조사를 통한 영양성분 추천
* 크롤링을 통한 영양 성분 정보 수집 > 데이터 가공하여 화면 구현
* 네이버 쇼핑 API를 활용하여 해당 영양성분에 대한 상위 랭킹 제품 리스트업 및 제품 상세 정보 제공
* 제품 찜하기 후 장바구니에 담기 > 그래프, 테이블을 활용하여 제품 비교
* SNS 소셜 로그인 (네이버, 카카오, 구글)
<br><br>
## 4. 사용언어 및 도구
![image](https://github.com/sin6338ki/HaruGungang/assets/130349912/b95be808-43bf-4e58-9e5e-06b3cb478273)

## 5. 유스케이스
![image](https://github.com/sin6338ki/HaruGungang/assets/130349912/dd970da0-1b01-4c95-b967-2d0514f04eeb)

## 6. 웹구성도
![image](https://github.com/sin6338ki/HaruGungang/assets/130349912/60b926e3-5d15-455d-bfc2-dcbad54e55c8)

## 7. 역할분담
![image](https://github.com/sin6338ki/HaruGungang/assets/130349912/1e2e19d4-966e-4c1d-a33d-99484b243576)

### 신지영
  * 프로젝트 팀장, **프로젝트 총괄 및 결과 발표**
  * 기획 및 목업 제작
  * 리액트 템플릿 적용 : 구 문법 적용에서 최신 문법 적용 (react-router-dom 5version >> 6version)
  * front-end & back-end
    * 설문조사 페이지 : 설문조사 진행, 결과(영양성분 추천) 기능 및 화면 구현
    * 메인 페이지 : 성별, 연령 선택 필터 기능 구현, 필터 선택 후 성별/연령별 추천 영양 성분 파이차트로 보여주는 기능 구현
    * 영양성분 상세 페이지 : 영양성분 DB에서 정보를 불러와 화면에 카드 형식으로 구현
    * 제품 상세페이지 : 제품 DB에서 정보를 불러와 카드 형식으로 화면 구현, 찜하기 버튼 클릭시 위시리스트에 저장되도록 기능 구현 및 DB 저장, 찜하기 취소 기능 구현
    * 위시 리스트 : DB에 저장된 위시리스트를 불러와 카드 형태로 화면 구현, 각 제품을 기능성별로 분류하여 배치
    * 동일 영양성분군 비교하기 & 서로 다른 영양성분 종합 정보 조회 : 위시리스트에서 체크박스로 선택한 1~3개의 상품을 하나의 페이지에서 비교할 수 있도록 화면 구현, DB에 저장된 정보를 recharts 라이브러리로 구현할 수 있도록 데이터 가공, recharts 및 테이블 활용하여 제품 비교 페이지 구현
### 서현록
  * 기획
  * REST API를 통해 네이버 API 정보를 불러와서 카드 형식으로 제품 화면 구현
  * 로고 디자인 및 웹 화면 디자인
  * Reactstrap/Bootstrap을 통한 웹 서비스 전체 스타일링 및 반응형 웹 적용
  * 초기화면에서 해당 서비스를 안내해주는 기능 구현
  * 공공데이터 가공
  * 최종발표 PPT 및 해당 웹서비스 소개서 제작
### 김신영
  * 회원가입, 로그인, 회원정보수정, 회원삭제 프론트엔드 기능 구현, 백엔드와 통신하여 회원정보 DB에 저장하도록 구현
  * 카카오톡, 네이버, 구글 로그인 기능 구현, 사용자 정보 요청하여 자동 회원가입 후 로그인하는 로직 구현
  * 로그인 후 로그인한 상태를 전역적으로 관리하고 페이지 이동 등 사용자 경험 개선을 위한 코드 작성
  * 사용자가 위시리스트에 담은 상품 숫자 항상 표시하도록 뱃지 기능 구현, 사용자가 찜 버튼 클릭할때마다 갯수 추적하여 반영
### 안영석
  * 화면 설계서 작성
  * 크롤링을 통한 영양제 정보 관련 데이터 수집
  * 공공데이터 가공
  * 데이터베이스 데이터 수집 및 가공

## 8. 트러블슈팅
### 8-1) 네이버 로그인 기능 구현중 CORS 에러 발생
  * 1차 해결 방안 : package.json에 proxy 추가
  * 결과 : 토큰 요청 주소와 사용자 정보 요청 주소가 달라 proxy 설정으로는 대응 불가
  * 2차 해결 방안 : http-proxy-middleware 라이브러리 설치 후 src 폴더에 setupProxy.js 파일 생성
### 8-2) react 템플릿 적용시 react-router-dom 구버전 설치로 구문법으로 작성된 코드
  * 해결방안 : 기존 버전 삭제 후 6버전 설치 후 ver6에 맞는 문법으로 코드 변경

  
