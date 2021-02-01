# turicreate
turicreate 사용법 및 기능 설명

## turicreate 설치 for Windows
[WSL, Linux distro을 이용한 turicreate 설치](https://blog.usejournal.com/installing-turicreate-on-windows-10-534e147a4792)
+ [GUI를 이용한 WSL, distro 설치](https://webdir.tistory.com/541)
+ [--use-feature=2020-resolver 에러 관련 해결법](https://stackoverflow.com/questions/63277123/what-is-use-feature-2020-resolver-error-message-with-jupyter-installation-on)
+ [turicreate interactive visualization not working 해결법](https://github.com/apple/turicreate/issues/2154)

추가 문제 해결
- [How to do plotting on WSL (Windows Subsystem Linux)](https://discourse.julialang.org/t/how-to-do-plotting-on-wsl-windows-subsystem-linux/32812)
- [Show matplotlib plots (and other GUI) in Ubuntu (WSL1 & WSL2)](https://stackoverflow.com/questions/43397162/show-matplotlib-plots-and-other-gui-in-ubuntu-wsl1-wsl2)

추가자료
- [WSL 소개](https://webdir.tistory.com/540)
- [MS wsl 설치 가이드](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## turicreate task focused toolkit 

추천시스템<br>
유저에게 개인화 추천을 제공할 수 있음, 과거 행동(interaction) 데이터를 통해서 모델링하고 모델을 활용할 수 있음<br>
<img src="https://lh5.googleusercontent.com/t1prsTMIOdSbVkByBOE6hZCb_TGl1MHp5YrdERASFAuh4y-7fy7GupYw6NHJlyxyswXx68kf4n3IYlFC5ILiAKXepBEmAIRSEH3msVtHXKfNirk6dWnF-MA0f459evSC4U4YrDPt"><br>
[* 출처 및 참고자료](https://davinci-ai.tistory.com/12)

**Image**
이미지 분류<br>
이미지를 기존에 정의한 몇몇의 라벨에 할당하는 작업, turicreate에서 쉽고 강력한 모델을 제공<br>
<img src="https://lh6.googleusercontent.com/-q-IUA_QiOVBliMtAOmlIB5lE9NYLohlCCFTsHwBZ2gJD0mFU8qZKDzmisfo0ItEstQ92cjldGqsJojPeaZq1Wtp2w2x7oqPELtSaYEFwMVlENRRTSNURO-ze9qFRrSDh9Oz2crT"><br>

그림 분류<br>
애플 펜슬, 마우스, 터치 인풋으로 주어진 그림에 대해 미리 설정한 클래스로 데이터를 분류할 수 있음<br>
<img src="https://lh5.googleusercontent.com/lvG7O-Ogal-aFDxwrUakIgJH3oME5NQhfuKF7n3V1ANUDzXMcWJrVuvey_HCDA9uZ2tqu2xkGGMBmH3DHfHqkrojXQXT2qzOls_GE3XPd8tV5DPhI43QT8jDJ-ThcbBpfjVaizwr">
쿼리로 아래의 이미지 추출<br>
<img src="https://lh5.googleusercontent.com/GLpmJro4uMLY4MijMiR9T_jz0tgGDmuH8RxNSVdRFAZKBsf9psOfJLMjl7EibVQSbNXOPJvzKe0I_E-_9mQT1CQ35Djk-FmQYq23ngnteQqCHPUTMpG7HoCUFEczoEHVzNR3DHHI">

## turicreate algorithm application in social network app

Recommender
- 콘텐츠 추천
- 사람 추천
- 태그 추천 (+ 검색 최적화)

Image Classification
- 콘텐츠 류

Drawing Classification
- 메모장 그림 등의 분류

Sound Classification
- 애기 울음소리, 개짖는 소리, 냄비 끓는 소리 등을 감지해 추가적인 행동을 취할 수 있도록 알림

Object detection
- 해시태그 추출, 이미지 분류 및 컨텐츠 군집화, 검색 카테고리 구성

One Shot Object Detection(similar to few shot learning)
- 2d 물체에 대해 적은 데이터로도 인식 가능

Style Transfer
- 스타일 변환, 새로운 테마 적용 등

Activity Classification
- 센서, 제스처(카메라에 그리기, 터치패드)로 어플 페이지 이동 등 기능 활용 가능

Classifiers
- 충성고객, 이탈고객 예측

Regression
- 고객 점수 스코어링 모델
- 콘텐츠 인기 점수 예측

Clustering
- 사용 데이터를 이용한 고객 군집화
- 고객의 행동(포스팅, 채팅)을 feature로 군집화

Text Classification
- 감성분석
  - 감성 점수 시각화
    문장 단위로 예측하고 scailing으로 '오늘의 감정' 등의 서비스 제공
    여러가지의 감정으로 카테고리를 나누고 카테고리별 점수를 나타내는 기능으로 고도화 가능

Visualization
- 카테고리컬 히트맵: 매칭 성향 분석(+mbti)
- 상대와 대화 빈도, 양 등을 통해 군집별 궁합 등의 기능 제공 가능

Additional
- 페이지 이동 분석으로 UX/UI 업그레이드 + 플로팅 버튼에 AI agent 적용
- 인공지능 feature 설계 데이터 분석
- 콘텐츠 기록, 해시태그 추출, 사용자 특성 파악 등을 활용하여 AI 설계
