욜로 https://ropiens.tistory.com/44 <br />
스펙 https://lv99.tistory.com/69 <br />
용어 https://ctkim.tistory.com/79 <br />
안드로이드 https://junyoung-jamong.github.io/machine/learning/2019/01/25/Android%EC%97%90%EC%84%9C-%EB%82%B4-YOLO%EB%AA%A8%EB%8D%B8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0.html <br />
다크넷 http://ngmsoftware.com/bbs/board.php?bo_table=study&wr_id=34&sca=%EB%94%A5%EB%9F%AC%EB%8B%9D <br />
JSON EDITOR https://jsoneditoronline.org/#right=local.sogeya  <br />
label https://supervise.ly/ <br />
python https://www.delftstack.com/ko/howto/python/ <br />

# Happy_moon_year

- 1만개의 QR코드 이미지를 yolo v5로 학습시켜 QR코드 인식을 해보자.
- 학습되어 나오는 .pb파일을 안드로이드에 심어서 카메라로 QR코드 인식하게 만들거임.
<br />
<br />

### 1. 컴퓨터 세팅하기
- yolo v5 다운 받고, cuda 세팅을 한다. 이하 생략

<br />

### 2. QR코드 이미지 1만개 다운받기
- https://www.kaggle.com/ 에서 이미지를 받아온다.
- 6 : 2 : 2로 train, test, validation로 분리한다.
- rename.py로 파일 이름을 변경한다. (ex. train1.jpg, train2.py...)

#### 2-1 이미지 1만개 라벨링하기
- 매우 귀찮고, 힘든 일에 봉착했음. 물론 나는 라벨링 따윈 안 할거임. 이론상이지만 QR코드는 검정색과 흰색으로 이루어져있음. 따라서 파이썬 코드를 짜고, QR이미지의 픽셀을 건드려서 bounding box를 떠볼거임. 안되면 이 과제는 포기임.

<br />
