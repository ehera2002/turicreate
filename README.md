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
