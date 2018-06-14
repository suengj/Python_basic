### 본 내용은 Python의 학습 방향을 정리하고자 작성한 노트입니다. (2018.06.14.)
### 작성자: 홍승재


#### 또한 현재 방향은 파이썬을 이용한 "데이터 분석"에 초점을 맞추고 있습니다.  	&#128526; 

#### 개요는 아래와 같습니다.

1. Python의 필수 개념 및 기본 함수 정리
    + 초기 개발 환경 구축
        + PIP, Anaconda, Jupyter Notebook, Atom 등 (~~<U>현재 수준에서는 작성하지 않을 계획</U>~~)
    + 기본 함수 (e.g., 작업 디렉토리 설정, 파일 입출력, 인코딩 문제 등)
    + R과의 차이점: 일대일 대응으로 비교가 불가능 할 것 같음
    
    
2. 핵심 패키지 정리 (\* 각 링크는 documentation 으로 연결되어 있음)
    + *수학 연산* - Matlab을 대체하기 위하여 작성된 라이브러리
        + [NumPy](http://www.numpy.org/): 수치해석 라이브러리
        + [SciPy](http://www.scipy.org/): 과학 기술 함수 라이브러리
        + [SymPy](http://www.sympy.org/): 심볼릭 연산 라이브러리
        
    + *데이터 처리* - R을 대체하기 위하여 작성된 라이브러리
        + [pandas](http://pandas.pydata.org/): 데이터 분석 라이브러리. R의 data.frame 자료구조 구현
    
    + *시각화* 
        + [Matplotlib](http://matplotlib.org/): 시각화 라이브러리, MATLAB 플롯 기능 구현
        + [Seaborn](https://stanford.edu/~mwaskom/software/seaborn/): 시각화 라이브러리. 통계용 차트 및 컬러맵 추가
        + [Bokeh](http://bokeh.pydata.org): 시각화 라이브러리. 웹상에서 인터랙티브 플롯 구현
    
    + *통계, 사회연결망 분석, 머신러닝 & 딥러닝*
        + [StatsModels](http://www.statsmodels.org/): 통계 및 회귀 분석, 시계열 분석 라이브러리
        + [Scikit-Learn](http://scikit-learn.org): 머신러닝 라이브러리
        + [TensorFlow](https://www.tensorflow.org/): 딥러닝 라이브러리
        + [Keras](https://keras.io/): 고수준 딥러닝 라이브러리
        + [KoNLPy](http://konlpy.org/en/v0.4.4/): 한국어 텍스트 분석
        + [NetworkX](https://networkx.github.io/documentation/stable/): 사회 연결망 분석
    
    + *크롤링*
        + [urllib](https://docs.python.org/ko/3/library/urllib.html) + [urllib3](http://urllib3.readthedocs.io/en/latest/#)
        + [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
        + [requests](http://docs.python-requests.org/en/master/)
        + [selenium](https://www.seleniumhq.org/docs/)
        + [phantomJS](http://phantomjs.org/documentation/)
        + [cron](https://help.ubuntu.com/community/CronHowto): only can be under UNIX-based computing system
        + [Web API] - not library (개념적인 부분은 별도로 검색 요망)
    + *데이터 베이스 (2018.06.14. 현재 필요하지 않아서 링크는 별도로 검색하지 않았음)*
        + [SQLite]
        + [MySQL]
        + [tinyDB]
        
---        
#### 주로 참고 한 자료는 다음과 같습니다. 
1. [데이터 사이언스 스쿨 내 라이브러리 소개](https://datascienceschool.net/view-notebook/b85212ea4040408e8ebd6d3495f2c91b/)
    + 덧붙여, [데이터 사이언스 스쿨 - Python version](https://datascienceschool.net/view-notebook/661128713b654edc928ecb455a826b1d/) 자체도 참고할만한 사이트입니다. 
    
    
2. 파이썬을 이용한 머신러닝, 딥러닝 실전 개발 입문 (쿠지라 히코우즈쿠에 지음, 윤인성 옮김 - 위키북스 데이터사이언스 시리즈) (2017)

3. [Python for Non-Programmers](https://wiki.python.org/moin/BeginnersGuide/NonProgrammers)

4. [Luis Solis' Blog](https://python.zeef.com/luis.solis) : ***강력하게 추천*** &#128525;

5. [점프 투 파이썬](https://wikidocs.net/book/1)

6. Introduction to Machine Learning with Python (Muller, Andreas C. & Guido, Sarah; O'Reilly) (2017)

7. Learning Python (Lutz, Mark; O'Reilly) (2013) - Python 이라는 프로그램 자체에 대한 내용에 가깝습니다. 

8. Python for Data Analysis (McKinney, Wes; O'Reilly) (2013):  ***추천합니다*** &#128525;

9. Automate The Boring Stuff with Python (Sweigart, Al) (2015) - Python을 통한 업무 자동화와 관련이 있습니다. (데이터 분석과는 거리가 있음)

10. Think Stats: Exploratory Data Analysis in Python (Downey, Allen B.; O'Reilly) (2014)


#### 덧붙여,
추가적으로 IPySTATA라는 라이브러리가 있다는 것을 확인하였습니다. (2018.06.15.)
대학원 과정에서 STATA를 주로 사용했는데, Jupyter Notebook에서 활용 할 수 있다는 내용 [[link 1 - github]](https://github.com/TiesdeKok/ipystata#setup) / [[link 2 - jupyter.org]](http://nbviewer.jupyter.org/github/TiesdeKok/ipystata/blob/master/ipystata/Example.ipynb) / [[link3 - pypi.org]](https://pypi.org/project/ipystata/) 을 보았습니다. 
