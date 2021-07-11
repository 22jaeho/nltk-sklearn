# nltk-sklearn

- Python, nltk, sklearn
- Google Colab

### 과정
- 데이터 불러오기 - 토큰화 - 빈도수 확인 - 인코딩 - 모델 학습
 
 
#### 데이터셋 명세

- train_set.csv
  - 수집기간 : 2020년 1월 1일 ~ 3월 31일
  - 기사 수 : 4597개
  - label 수 : 5074개
- test_set.csv
  - 수집기간 : 2020년 6월 1일 ~ 6월 30일
  - 기사 수 : 1500개
  - label 수 : 1602개
- label_info.txt
  - train, test set의 label 값이 의미하는 실제 카테고리 정보
- 대부분의 label은 실제 데이터의 label 분포를 따름
   - 대기 label 데이터는 양이 너무 많아, 실제 데이터보다 적게 추출
   - 지질, 지형, 토양 데이터는 양이 너무 적어, 실제 데이터보다 많이 추출
- 하나의 기사가 여러 개의 label로 분류될 수 있으며 후술할 id를 통해 복원 필요

#### 데이터 attribute 명세

- id : (int) : 텍스트의 고유한 id
- label : (int) : 15종 + 분류외 + 환경데이터 아님까지 총 17종 label 분류(label_info.txt에 명세)
- text : (char) : 뉴스 기사. [제목] 내용 형태로 이루어짐
- 특이사항
  - 중복 id : 동일한 id를 가진 두 개의 tuple이 존재할 경우, 같은 기사가 두 개의 label로 분류된 것임
