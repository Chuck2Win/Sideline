# 1. pdf 논문 들을 text로 변환
# 2. dictionary에 해당하는 부분 추출
# 3. QA 이후 부분만 추출

## 관련 패키지
1. pdftotext
  설치 안되는 이슈
  conda install -c conda-forge poppler
  pip install pdftotext
  -> 그냥 colab에서 실행하자
  ! apt install build-essential libpoppler-cpp-dev pkg-config python3-dev
  ! pip install pdftotext

## 사항 정리
1. pdf2text
2. questions and answers 부분 추출
-----
추가 이슈 1: questions and answers 부분이 과연 이 단어로만 구성되어 있을까?
추가 이슈 2: dictionary를 보니, `_` 로 연결되어 있음 -> 이 부분의 경우 하이픈으로 연결한 경우를 찾거나, n gram을 찾아야할 것 같음
            -> TreebankWordTokenizer를 활용하고, n gram (4)까지 해서 Counter를 활용해서 처리하자.
            
            
