# 1주차 정리

| 주제   | 내용         |
| ---- | ------------- |
| position | static, relative, absolute, fixed, sticky에 대해 알아봅니다. |

## 1. Position의 정의
&lt;tag>의 위치를 결정해주는 중요한 속성이다.
position만 정확히 안다면 홈페이지를 만들 때 위치 지정은 아주 손쉬울 것!
position을 정한 다음 top, right, bottom, left가 최종적으로 요소의 위치를 정해준다.

## 2. Position 속성의 종류

### 2.1 position : static

position을 따로 지정해주지 않았을 때 태그의 기본 값이다.
원래 자기가 있어야 하는 위치에 존재한다.
top, right, bottom, left, z-index 속성이 먹지 않는다.

### 2.2 position : relative

원래 자기가 있어야 하는 위치를 기준으로 top, right, bottom, left 값에 따라 위치가 정해진다.
top, right, bottom, left 속성이 정해지지 않으면 원래 있어야 할 위치에 자리잡고 있다.
z-index 의 값이 auto가 아니라면 새로운 쌓임 맥락을 생성한다.
부모 태그의 위치가 달라지면 그 위치에 비례해서 같이 움직인다.
무조건 부모가 기준!

### 2.3 position : absolute ← 우리가 제일 많이 사용한 속성

position 속성이 static이 아닌 부모를 기준으로 top, right, bottom, left 값에 따라 위치가 정해진다. 모든 부모가 static이면 body를 기준으로 위치를 잡는다.
top, right, bottom, left 속성이 정해지지 않으면 원래 있어야 할 위치에 자리잡고 있다.
부모로 부터 자유로워지며 부모가 제공해준 크기가 아니라 자신의 컨텐츠 크기 만큼 너비, 높이를 차지하게 된다.

### 2.4 position : fixed

내용 placeholder

### 2.5 position : sticky

------

질문, 이해가 안 갔던 것, 궁금한 것, 스터디장이나 다른 사람들에게 물어보고 싶은 것, 기타 등등이 있으시면 써주시고, 이 문구는 지워주세요!
