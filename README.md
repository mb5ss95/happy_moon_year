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

### 3. 이미지 1만개 라벨링하기
- 매우 귀찮고, 힘든 일에 봉착했음. 물론 나는 라벨링 안 할거임. 언제 다해.. 
- 이론상이지만 QR코드는 검정색과 흰색으로 이루어져있음. 따라서 파이썬 코드를 짜고, QR이미지의 픽셀 어레이를 불러와 bounding box를 떠볼 생각임.
- 아니면 그냥 해상도 그대도 라벨링해도 되지 않을까 생각이 듬.
- QR코드는 흰검으로만 이루어져 있어 학습이 왠만하면 잘 될 것 같아서 yolov5s 모델로 해보기로 했다.
#### 3-1 이미지 라벨링 파이썬 코드 짜기
- yolo v5 데이터 포맷은 (class_id center_x center_y width height)로 이루어져 있다. 
- https://stackoverflow.com/questions/69729085/how-can-i-convert-dataset-annaotations-to-fixedyolov5-format-without-hand-enco 에서 보면 이미지의 전체 해상도를 1, 1로 잡고, center_x center_y width height 값을 비로 잡은 것 같다. 이를 구현하려면 연산이 필요 할 것 같다.
- 픽셀 어레이에서 첫 번째로 RGB가 검정(0, 0, 0)일 때의 xy 값을 구하고 전체 해상도와 계산하여 QR코드 정사각형의 가로세로 길이와 중앙 xy값을 찾음.
- label.py로 1만개의 이미지 연산을 통해 라벨링을 완료하였다.
<br />
