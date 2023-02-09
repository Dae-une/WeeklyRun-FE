![KakaoTalk_Photo_2022-10-04-16-55-33](https://user-images.githubusercontent.com/104764474/193819731-ab83241b-e3b6-4dee-90b4-738e58a6c18e.png)

<br/>
# WeeklyRun
런닝을 하고 싶은데 동기부여가 있으면 좋겠나요?<br/>
한 주간의 목표를 세우고 매일매일 기록을 확인하며 <br/>
유저들과 피드를 공유해보세요!

# [Demo영상](https://www.youtube.com/watch?v=wmHWVBSeeHE)

# 주요기능
### 1. 로그인
* 네이버 와 카카오를 활용한 소셜로그인으로 간편하게 로그인 가능합니다.
### 2. 목표 설정하기
* 한 주간의 목표를 설정하고, 하루하루의 기록을 볼 수 있습니다.
### 3. 런닝 기록하기
* 실시간 위치를 기반으로 런닝을 추적하며 기록 및 피드를 통해 공유할 수 있습니다.
### 4. 피드
* 최신순 및 좋아요 순으로 정렬하여 볼 수 있습니다.
* 좋아요 및 답글,대답글을 이용할 수 있습니다.
### 5. 검색하기
* 해시태그 및 유저 이름을 자동완성 기능을 이용하여 검색할 수 있습니다.
### 6. 답글페이지
* 답글을 입력 할 수 있으며, 슬라이드를 이용하여 수정 및 삭제 가 가능합니다.
### 7. 신고하기 기능
* 부적절한 게시글 을 신고 하거나, 이용중에 발생한 문제에 관해 신고할 수 있는 별도의 페이지가 존재합니다.


# 기술스택
<div align="center">
  <img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white"> 
  <img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"> 
  <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> 
  <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"> 
  <br/>
  <img src="https://img.shields.io/badge/react Query-FF4154?style=for-the-badge&logo=react-Query&logoColor=black"> 
  <img src="https://img.shields.io/badge/recoil-61DAFB?style=for-the-badge&logo=recoil&logoColor=black"> 
  <img src="https://img.shields.io/badge/styledcomponents-DB7093?style=for-the-badge&logo=styled-components&logoColor=white"> 
  <br/>
   <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"> 
   <img src="https://img.shields.io/badge/githubactions-181717?style=for-the-badge&logo=githubactions&logoColor=white"> 
</div>

# 아키텍쳐
![스크린샷 2022-10-03 오후 1 38 59](https://user-images.githubusercontent.com/104764474/193502802-0399a082-4875-405b-9bec-bac7749a3511.png)


# 라이브러리
### 1. React Query
* 기존 부트캠프 과정을 수료하는동안 글로벌 스테이트를 관리하기 위하여 Redux 라이브러리를 주로 사용했습니다. <br/>
 Flux패턴을 이용하여 예측가능한 데이터 플로우를 그릴 수 있다는 점과 데브 툴을 활용하여 직접 볼 수 있다는 점은 좋았으나 <br/>
 비대한 보일러 플레이트의 단점과, 클라이언트 데이터를 관리하기엔 적합할 순 있어도,<br/> 
 서버 데이터를 관리하기에는 아쉬움이 너무 많았습니다.
* 저희 프로젝트는 작은 사이즈이기는 하지만, 클라이언트의 복잡도가 높지 않고,<br/>
  각 페이지에서 공통적으로 사용하는 글로벌 스테이트 또한 적었습니다.<br/>
  따라서 클라이언트 데이터 보단 서버데이터에 많은 비중을 두고 있어,<br/>
  서버 데이터를 관리할 효율적인 툴이 필요하였습니다.<br/>
  이에 대한 대안으로 SWR과 React-Query에 대해 공부하였습니다.
* 두 라이브러리 모두 mutate, Optimistic UI등 비슷한 기능을 제공하지만<br/>
  데브 툴을 정식으로 지원하며, 전체적으로 조금 더 기능이 많은 React-Query를 채택하였습니다.
  
### 2. Recoil
* React-Query를 채택함으로써, 클라이언트 데이터를 관리할 툴이 필요했습니다.<br/>
  대안으로 Recoil과 Context API를 두었지만,<br/>
  Context API는 상태 변화가 일어날 경우, 구독하고 있는 모든 컴포넌트가 리랜더링이 되며,<br/>
  하나의 value만을 저장할 수 있다는 단점이 있었습니다.<br/>
* 저희는 Recoil의 쉬운 러닝커브와, slector를 이용한 다양한 데이터 변환이 가능하다는점이 <br/>
  매력적으로 느껴져, Recoil을 채택하였습니다.
  
### 3. @lodable/component
*  Code Spitting 을 활용하여, 불필요한 페이지의 컴포넌트까지 읽어오는것을 막아<br/>
   초기 로딩속도를 빠르게하여 UX를 높이고 싶어 채택하였습니다.
*  Code Spitting 이란 ? <br/>
앱의 규모가 커짐에 따라 Bundling 되어 제공되는 파일의 사이즈도 커지게 됨으로써 앱의 로딩 속도가 느려지게 된다.<br/>
이러한 문제를 해결하기 위해 Code Splitting을 적용하여 <br/>
현재 필요한 모듈만 로딩(lazy-load) 되도록 하여 성능을 향상시킬 수 있다.

### 4. browser-image-compression
* 프로젝트 특성상 많은 이미지를 사용할 수 밖에 없습니다.<br/>
  이때, 이미지의 용량이 크고, 양이 많다면 로드 하는데 소요되는 시간이 길어질 것이라 예상하였습니다.<br/>
  따라서, 이미지를 업로드 할때 이미지의 사이즈를 줄이고자<br/>
  조금 더 나은 UX를 제공하고자 사용하였습니다.

### 5. Yarn Berry
* 여태까지는 패키지 관리 시스템으로 npm을 사용해 왔습니다만,<br/>
  npm을 사용하던 중, node_modules의 막대한 사이즈나,가끔 발생하는 에러가 아쉬웠습니다.<br/>
  그러던 중, 다른게 없을까 하다 Yarn Berry에 대해 알게되었습니다.
* Yarn Berry는 Yarn 과는 다르게 PnP전략을 이용하였습니다.<br/>
  이 PnP로 인하여, npm의 의존성을 찾기위해 그 많은 폴더를 다 순회할 필요 없이<br/>
  .pnp.cjs파일이 제공하는 자료구조를 이용하여 의존성을 찾고 이로써 import하는 시간이 단축된다는 점과<br/>
  엄격한 의존성 관리를 하여 유령 의존성을 막으며 <br/>
  비대한 node_modules의 사이즈를 대폭 줄여준 다는 점이 좋아 채택하였습니다.
  

# 트러블 슈팅
<details>
  <summary>위치를 불러오는 함수와 시간 타이머 함수를 시작 버튼 ,정지 버튼 및 종료 버튼을 이용하여 제어할 수 있어야하며, 일정한 시간 간격으로 함수가 작동해야함</summary>
  <div markdown="1">
    useInterval 커스텀 훅을 사용하여, callback 함수와 delay를 파라미터로 넘겨 delay가 null일 경우 함수가 중단됨
     자세한 내용은 https://velog.io/@dae_eun2/React-useInterval 에서 확인 가능합니다.
    
  </div>
</details>
<details>
  <summary>검색어 입력시 불필요한 요청 및 상태변화가 일어남 </summary>
  <div markdown="1">
    
      검색 인풋에 글씨가 입력될때마다 요청이 간다면 불필요한 요청이 생길뿐만아니라 과도한 요청이 발생할 수가 있음 
      debounce 훅을 만들어서 , value와 delay를 파라미터로 받으며, <br/>setTimeout을 이용하여 일정 시간 동안의 이벤트 발생을 무효화시켜
      change되는 value값의 시간 텀을 조정하여 사용
    
  </div>
</details>
<details>
  <summary>게시글 수정에서 이미지 변경시 데이터 타입에 관한 에러 발생</summary>
  <div markdown="1">
    업로드 이미지를 blob타입으로 백엔드에 넘겨주는데, 기존 이미지는 string타입으로 url주소로 받음 <br />
    기존이미지를 blob타입으로 변경 하여 줄 수가 없어, 기존 이미지를 수정하는것에대한 문제가 발생함 <br />
    
      해결방안 
      백엔드에 prevImage와 newImage를 별도로 전송하여 백엔드측에서 newImage를 업로드 후, prevImage로 합치게끔 하여 문제 해결
    
  </div>
</details>


# 프론트 엔드 팀원
|팀원|깃허브 주소| 역할 분담|
|----|-----|------|
|김대은| https://github.com/Dae-une   | 초기세팅(eslint,prettier), 기록하기, 게시글 작성, 랭킹페이지, 신고하기,<br/> 검색기능, 댓글 페이지, GitHub Actions, S3,CloudFront를 이용한 배포 |
|김도우|  https://github.com/dowoo99  | 유저페이지, 피드페이지 |
|이승준|  https://github.com/lsj3284   | 로그인 페이지,댓글페이지 |
