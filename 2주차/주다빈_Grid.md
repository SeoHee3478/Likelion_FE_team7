# 2주차 정리

| 주제   | 내용         |
| ---- | ------------- |
| 주제 | 구체적인 내용 |
| 1. Grid란? | Grid의 개념 및 속성 |

## 1. Grid란?

### 1.1 Grid의 정의 

행과 열로 된 2차원 레이아웃 시스템으로 엑셀이나 <table>과 비슷하다고 생각하면 쉽다.

* grid : Block 특성의 Grid Container를 정의
* inline-grid : Inline 특성의 Grid Container를 정의

| 행 | 열 |
|--|--|
| row | column |
| height| width|

**Flex와의 차이점**
Flex는 비교적 단순한 1차원 레이아웃을 위하기 때문에, 더 복잡한 레이아웃을 사용해야 할 때 Grid가 유용하다.


### 1.2 Container(컨테이너)와 Item(아이템)

![](https://blog.kakaocdn.net/dn/d9PTuu/btrzAWpocXn/Fpqbtn29soq7uxseFaRM11/img.png)
출처: 위니브

그리드 컨테이너 : 그리드의 가장 바깥 영역
그리드 아이템 : 그리드 컨테이너의 자식 요소들
그리드 트랙 : 그리드의 행(row) 또는 열(column)
그리드 셀 : 그리드의 한 칸 (개념적인 정의)
그리드 라인 : 그리드 셀을 구분하는 선
그리드 넘버 : 그리드 라인의 각 번호
그리드 갭 : 그리드 셀 사이의 간격
그리드 에어리아 : 그리드 셀의 집합


## 2. display:grid;
해당 속성만 적용할 경우 지정된 높이에 맞게 stretch된다.
px, fr, %의 단위를 사용할 수 있고 repeat이란 값을 이용하여 할 수 있다.

👀fr이란? 
fr이란 유연한 크기를 갖는 단위로
그리드 컨테이너 내의 공간 비율을 분수(fraction)로 나타낸다.

사용자가 계산해야 할 부분을 fr을 통해서 쉽고 유연하게 사용할 수 있습니다.

### 2.1 grid 적용 전, 후

**display: grid; 적용 전**
![enter image description here](https://blog.kakaocdn.net/dn/SpS5T/btrzx9XF9Lb/CdVvv2FIHQpVaunTlITfOK/img.png)

**display: grid; 적용 후**
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/bsirbD/btrzEBSfNCM/8N3WKyM60i75Kf8HBsbvJk/img.png)


### 2.2 Grid의 row / column

* **grid-template-columns** : 열의 넓이를 설정한다.
* **grid-template-rows** : 행의 높이를 설정한다.
* **repeat**( 적용할 트랙의 갯수, 반복할 수치 ) 함수를 이용하면 그리드 트랙 별 수치 반복을 설정 할 수 있다.
* 열과 행의 값을 반복 시키는 최신 문법은 repeat(12, 1fr 20px)입니다.


### grid-template-columns의 테스트(row 지정 x)
``` 
grid-template-columns: 200px 500px 200px;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/oAyqn/btrzAUSGsR7/StN3ti9qmTP1LzJuO5aipK/img.png)

``` 
grid-template-columns: 1fr 2.5fr 1fr;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbJlDaZ%2FbtrzyahRoAM%2FUzU7K1Y6mtP2GT3rvbMMY1%2Fimg.png)

``` 
grid-template-columns: repeat(3, 1fr);
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb1Flqf%2FbtrzAWCVXXV%2FlkpgmAMDBCfqx3Y3IFNSWK%2Fimg.png)


### grid-template-columns의 테스트(row 지정 x)
``` 
grid-template-rows: 200px 500px 200px;
```

* 이렇게 3개만 지정했기 때문에 한 줄씩으로 생각하여 위의 3개만 영역이 잡힌것을 확인할 수 있다.

![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F4dlob%2Fbtrzz42iz9Z%2FnzMQ0TxQ95JxfHPeqtzzF0%2Fimg.png)

columns의 속성(repeat(3, 1fr);) 을 함께 사용한다면
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/bUlN1P/btrzzqLjlwZ/2Ujssxa3g4Ph1bnGTQc66k/img.png)

``` 
grid-auto-rows: 200px;
```
* 모든 행들의 높이가 동일하게 지정되었다

![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fcd0jxI%2FbtrzDusb97A%2FJ0MhO4PYrmPK2srIK2mZE0%2Fimg.png)



### 2.3 minmax()

CSS 그리드 전용의(현재까지는) 크기 조절 함수로 최솟값과 최댓값을 넣으면 열이나 행이 그 사잇값으로  알아서  줄어들고 늘어난다.
max  <  min  이면  max  는 무시되고  min  으로  minmax(min,max)처리된다.  

1. max-content
그리드 트랙을 차지하는 그리드 항목의 최대 콘텐츠 기여도를 나타낸다.

2. min-content
그리드 트랙을 차지하는 그리드 항목의 가장 큰 최소 콘텐츠 기여도를 나타낸다.

3. auto
최대값과 동일합니다  max-content.  최소한 그리드 트랙을 차지하는 그리드 항목  의 가장 큰 최소 크기(  [min-width](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width)/ 로 지정됨)를 나타낸다.

### 🚨  auto를 사용할 때의 문제!
IE 11에서는 미지원하기때문에 IE를 챙겨줘야한다.


## 3. Gap
(행, 열)로 각각 다른 값을 부여할 수 있고 하나만 입력할 경우 동일하게 적용된다.

### 3.1 gap
```
gap: 20px;
gap: 20px 20px;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fcd0jxI%2FbtrzDusb97A%2FJ0MhO4PYrmPK2srIK2mZE0%2Fimg.png)


### 3.2  row - gap
```
row-gap: 20px;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdSCN7I%2FbtrzCLOuLvN%2FS9TGC9E3aw374ze3P31IEk%2Fimg.png)

### 3.3  column - gap
```
column-gap:20px;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdSCN7I%2FbtrzCLOuLvN%2FS9TGC9E3aw374ze3P31IEk%2Fimg.png)


### 🚨 gap을 사용할 때의 문제!
IE에서는 gap의 대체 속성이 없어서 IE에서의 사용을 고려한다면 처음부터 gap을 사용하지 않아야 한다. gap을 사용하지 못한다면 margin으로 해결하면 된다.


# 3. 각 셀의 영역 지정
| 속성 | 의미 |
|--|--|
| **grid-row-start** | 그리드 아이템(Item)의 행 시작 위치 지정 |
| **grid-row-end** | 그리드 아이템의 행 끝 위치 지정 |
| **grid-row** | grid-row-xxx의 단축 속성(행 시작/끝 위치) |
| **grid-column-start** | 그리드 아이템의 열 시작 위치 지정 |
| **grid-column-end** | 그리드 아이템의 열 끝 위치 지정 |
| **grid-column** | grid-column-xxx의 단축 속성(열 시작/끝 위치) |

```
grid-column-start: 1; 
grid-column-end: 3; 
grid-column: 1 / 3; 

grid-row-start: 1; 
grid-row-end: 3; 
grid-row: 1 / 3;
```
![enter image description here](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/Iwbwt/btrzEBLpfEJ/9EUvwuYSkNmXfoSkyhg7Hk/img.png)

분수가 아니고, 1번부터 3번까지 공간 차지한다는 의미이다.

여기서 헷갈리는게 1부터 3까지인데 왜 두 칸만 지정되었는지 의문이 들 수 있다.

grid는 1,2,3라인으로 되어있기에 그런것이다.