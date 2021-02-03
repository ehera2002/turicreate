# turicreate
turicreate 사용법 및 기능 설명

## turicreate 설치 for Ubuntu

The minimum requirements are:
 - python 2.7, 3.5, or 3.6 (support for 3.7 pending #788)
 - glibc >= 2.10 (Centos >= 6, Ubuntu >= 9.10, or equivalent)
 - For Neural Network support, glibc >= 2.17 is needed (Centos >= 7, Ubuntu >= 13.04, or equivalent)
 - libstdc++ >= 6.0.19 (Ubuntu >= 14.04 or equivalent, or GCC 4.8.3 or later)
 - libgconf-2-4 (on Ubuntu 17.10 and later)

### Ubuntu >= 17.10

Follow the instructions for Ubuntu >= 14.04, but also install `libgconf-2-4`. This was previously included in desktop Ubuntu distributions but now needs to be installed separately starting with 17.10.

### Ubuntu >= 14.04
On recent versions of Ubuntu, we just need a few dependencies

```shell
sudo apt-get install -y libstdc++6 python-setuptools
sudo easy_install pip
sudo pip install virtualenv
```

To avoid making system changes, we are going to do everything in a virtualenv

```shell
cd $HOME
virtualenv venv
```

Activate the virtualenv

```shell
cd venv
source bin/activate
```
Install turicreate

```shell
pip install --upgrade pip
pip install turicreate
```

### Ubuntu < 14.04
(Tested on Ubuntu 12.04)

Compiling gcc from source is necessary here.
You can download any version of gcc >= 5 from https://gcc.gnu.org

```shell
sudo apt-get install gcc g++

cd ~
wget https://mirrors-usa.go-parts.com/gcc/releases/gcc-7.2.0/gcc-7.2.0.tar.gz
tar -xzvf gcc-7.2.0.tar.gz
cd gcc-7.2.0
contrib/download_prerequisites
./configure --disable-multilib --enable-languages=c,c++ --disable-bootstrap
make
sudo make install
```


Every time you open a new bash session, you should run the following commands. You could put them in `~/.bashrc` for convenience.

```shell
export LD_LIBRARY_PATH=/usr/local/lib64:$LD_LIBRARY_PATH
```

To avoid making system changes, we are going to do everything in a virtualenv

```shell
cd $HOME
virtualenv venv
```

Activate the virtualenv

```shell
cd venv
source bin/activate
```

Install turicreate

```shell
pip install --upgrade pip
pip install turicreate
```

\* ref: [**Linux Installation Instructions**](https://github.com/apple/turicreate/blob/master/LINUX_INSTALL.md#ubuntu--1710)

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

## GPU 환경 설정 for turicreate
- turicreate GPU는 tensorflow를 이용하기 때문에, CUDA, CuDNN과 함께 종속성에 맞춰 설치해야함


## turicreate GPU
- turicreate supports GPU versions on Ubuntu and macOS

사용법<br>
\# Use all GPUs(default)<br>
turicreate.config.set_num_gpus(-1)<br>

\# Use only 1 GPU<br>
turicreate.config.set_num_gpus(1)<br>

\# Use CPU<br>
turicreate.config.set_num_gpus(0)<br>

## turicreate task focused toolkit 

- 추천시스템<br>
유저에게 개인화 추천을 제공할 수 있음, 과거 행동(interaction) 데이터를 통해서 모델링하고 모델을 활용할 수 있음<br>
<img src="https://lh5.googleusercontent.com/t1prsTMIOdSbVkByBOE6hZCb_TGl1MHp5YrdERASFAuh4y-7fy7GupYw6NHJlyxyswXx68kf4n3IYlFC5ILiAKXepBEmAIRSEH3msVtHXKfNirk6dWnF-MA0f459evSC4U4YrDPt"><br>
[* 출처 및 참고자료](https://davinci-ai.tistory.com/12)

**Image** <br>
- 이미지 분류<br>
이미지를 기존에 정의한 몇몇의 라벨에 할당하는 작업, turicreate에서 쉽고 강력한 모델을 제공<br>
<img src="https://lh6.googleusercontent.com/-q-IUA_QiOVBliMtAOmlIB5lE9NYLohlCCFTsHwBZ2gJD0mFU8qZKDzmisfo0ItEstQ92cjldGqsJojPeaZq1Wtp2w2x7oqPELtSaYEFwMVlENRRTSNURO-ze9qFRrSDh9Oz2crT"><br>

- 그림 분류<br>
애플 펜슬, 마우스, 터치 인풋으로 주어진 그림에 대해 미리 설정한 클래스로 데이터를 분류할 수 있음<br>
<img src="https://lh5.googleusercontent.com/lvG7O-Ogal-aFDxwrUakIgJH3oME5NQhfuKF7n3V1ANUDzXMcWJrVuvey_HCDA9uZ2tqu2xkGGMBmH3DHfHqkrojXQXT2qzOls_GE3XPd8tV5DPhI43QT8jDJ-ThcbBpfjVaizwr">

- 이미지 유사도<br>
feature 분석을 통해 유사한 이미지를 찾는 것이 목적, 이미지 분류와 달리 모델링을 위해서 이미지 라벨링이 필요 없어 더욱 쉽게 처리 가능<br>
<img src='https://lh5.googleusercontent.com/-sdJYIE0PBOrweL-DG3WOUzFC65qFDOGzDYJeo9ervzB5cvdVl2158d6UtvqD0EjNS-reKDzdPonjqzqo7RzvZ2TbVkAJL2gWEq5swA9tyd98LVYNyq2kbAgy9SKx7kAkwEs55_9'>
쿼리로 아래의 이미지 추출<br>
<img src="https://lh5.googleusercontent.com/GLpmJro4uMLY4MijMiR9T_jz0tgGDmuH8RxNSVdRFAZKBsf9psOfJLMjl7EibVQSbNXOPJvzKe0I_E-_9mQT1CQ35Djk-FmQYq23ngnteQqCHPUTMpG7HoCUFEczoEHVzNR3DHHI">

- 물체 탐지<br>
물체를 분류하고 위치를 찾는 작업, 주어진 이미지에 박스 바운딩과 물체 클래스를 제시<br>
<img src="https://lh6.googleusercontent.com/l1EP49zjVCHZYhzTDUj_6gBf3JHQ_FF2W4p72pBz7kVwQyExsJEQvmYLOXSy3yGey1JyiE4llaWaD4ZKSQv6a58OQBcwS_a9TT8_03I6Au5AHzaEnM2pOPfd8LCbLU-T8TkgJQbQ">

- 원샷 물체 탐지<br>
클래스별 적은 양의 데이터로 플랜카드, 표지판, 로고 등 2차원 이미지에 대해 빠른 성능 보여줄 수 있는 물체 탐지<br>
\* 얼굴, 동물, 차와 같은 3차원 데이터는 위의 물체 탐지가 더욱 적합
<img src="https://lh3.googleusercontent.com/ncnjglHxfuvBw2xIWDlwx4F2UEuN0NF5Iezi8gSce8fNEqhQ4cUXJrXYKAgrhwLL1KPuC1jGf7aSAAjc1_CdSBh6_nx7Pp98iOu9YmjEK-EZr2KiWag4fwSHKStLAxQIjzipvKo_"><br>

\* 비교

|   |원샷 물체 탐지|투샷(위치, 분류) 물체 탐지|
|---|---|---|
|장점|높은 실시간성|높은 정확도|
|단점|정확도는 투샷 물체 탐지에 비해 낮음|학습과 테스트 속도 느림|

[* 출처 및 참고자료](https://mickael-k.tistory.com/24)

- 스타일 변경<br>
스타일 이미지를 구성하고 새로운 이미지가 주어졌을 때 새 이미지의 컨텐츠는 보존하면서 스타일을 변환시켜주는 작업<br>

스타일 이미지와 컨텐츠 이미지<br>
<img src="https://lh4.googleusercontent.com/khwL_2z8W7jTJZTsE9MS_tVkOzpDVP126RYWD6mNs94jUHccjHqs21IqtZvneEqVazCOD9DpQoVbYmYd9N4UzcxKc71AZJt2G8jCnfgAS6Ecp24RfQHivTUnVtFhP8SfH_c05qfB"><img src="https://lh6.googleusercontent.com/Vk9Fdqh07x94JYnwooDzH838sYhggu19SjbZ6BAw0okq1IGmy9jwUKSokae_3CUn0sVDdDPJWzQ5h-6dvO03J3kPIXlFmm7VCWaCEBI8EyEmd61ZAws8fd1aWiuWlB9xNosYAXhm"><br>
변환된 이미지<br>
<img src="https://lh3.googleusercontent.com/puMKhoyM57nfQeAplbS9Hh_z7swu6Ab4qaBKdHoPPbGN6KwTORn7EuAFJ7KXouBrUdaUf18bbEeXtufAvi-G_UFVRisfqtahz96mfDRzYcqPBpXx1gxC3h9n6L-UrGMqTVWc49NO">

- 사운드 분류<br>
주어진 사운드(ex. wav파일)를 할당된 라벨에 분류하는 작업 * 음성 인식(speech recognition)과는 다른 작업<br>
<img src="https://lh5.googleusercontent.com/fL8E-u0lMgB5p1RPl6V8ftbU4CMH0DGoLbrUTVKkGljUIaL6ikX-MFse_SiaKdOA4yxZ4B8zTlPWHwO6suOLu50_od9h6yTphbUrf6UHNd7RfbnePQuWt8jNeKdz5t8cYnF28rxD">

- 행동 분류<br>
가속도계, 방향과 각도의 변화에 대한 속도, 온도 등 센서 데이터로 학습하여 동작을 감지하는 작업, 특정 제스처로 메시지 읽기, 전화걸기 등으로 응용 가능<br>
<img src="https://lh3.googleusercontent.com/lvTsAu4ZZ71MqG2ovZw775mVcoNwXy3zcTzByOe_QF2PNcoKeSMe-RQvQLUS5SCGxKMwAATxAx01GKHadvQNm604OUg2LAeOQ46Dnwtg4QapdGWjdItqeE4GltTy7x5iWVMpux5S"><br>
\* 데이터(motion-sensory input) 예시
[* 참고자료](https://medium.com/skafosai/activity-classification-with-create-ml-coreml3-and-skafos-part-1-8f130b5701f6)

- 텍스트 분류<br>
감성 분석과 같은 업무에 주로 사용되고, 사용자의 요구와 상품 및 서비스가 일치하는지 분석할 수 있음<br>
  - 포럼 리뷰 데이터: 다양한 상품과 특징에 대해 사람들이 어떻게 느끼는지 분석 가능<br>
    <img src="https://lh3.googleusercontent.com/2Aw2EwfSMWGmXoIQpmptoJeS9yZULKCWWBs-u1QkfcvX3jk0_usSPM7W8TWSEOeU-ZRngcbR2FDg-0nFORRcN2VTymorXPG0trZhqTZ5CuiuuUuol5aUEB0rT51GWlQbV2tH3fNP">
  - 레스토랑, 영화 리뷰: 사람들이 열광하는 부분 실망하는 부분 분석<br>
    <img src="https://lh3.googleusercontent.com/sLstr2VIQrwFR2Q-uCH9bjfs298yTOgBAGxzgXdOGT62_E1nFkXQyLf4GEmv8fA5KFjJqGt3mk4bmJ0JEt_St1cp6BRshptB0eXczfzaylNrW5oYWo-Nnzm0cThjRxXolneF2PDo">
  - 소셜 미디어: 회사, 정치인 등 Hashtag에 대한 감성분석 + 블로그 댓글 분석으로 타겟 방문자의 감성 분석<br>
    <img src="https://lh5.googleusercontent.com/YPegIhOaJK9HTUpslnfhIlYnI-2KJ_ll2W2vmfUYfcxtjBsOjczACMRMQbRWxDfL5OdT70Wu9OH53BWjWVYFPAwGIYbVhL9uwVg12KcJlB0GmMC-zyd4qOOO4nyvjRMnVFwooKC0" width=380><img src="https://lh6.googleusercontent.com/3s394t1Y4qu3PiTvoUzjbUcrf9WWTVFabr6N2c6j8_P8GXRY3Gw-2xa1gxOFAsp25fcy-_zgVH3Bn0QnfLqfl-mA0l0PcXFRYICbZ_UdkGYkJHJvkcYcLGi1BC7Cvck1pgp4xBtm" width=380><br>
  - 콜센터 통화내역: 고객이 선호하거나 불만을 가지는 토픽에 대한 분석<br>
    <img src="https://lh3.googleusercontent.com/_C6pM-zeffiek-XyvagoaUZJEbXO0cwK8AYdR23xjEsY_5aZGu5ymvkIMK0VJ5t424sNlYDBDHcKtHBzgVbTTdHcUT_sPWZI6Z_1YADU0s0wTKOGhkz3JiM9sYNwQoK4wdJzlxj8">
  
    



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
