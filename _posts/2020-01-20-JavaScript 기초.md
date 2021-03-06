---
title: "JavaScript 기초"
categories: 
  - 교육
last_modified_at: 2020-01-20T13:00:00+09:00

toc: true
---
2020.01.20

2020.01.17 김성호 책임님의 Javascript 기초 교 토대로 작성하였습니다.

### script

script 안에 코드 직접 쓰면 전역에 저장됨.

### use strict

사소한 것까지 경고가 나오게 ( 제약사항 체크)

### DOM

브라우저 빌트인 API
브라우저에서 js를 다룰 수 있도록 처리

### HTML은 위에서부터 한 줄씩 실행 (선언안하고 사용하는 경우 문제 생김)

해결 1 : 스크립트 위치를 BODY 태그 끝으로 옮김.
해결 2 : window onload 이벤트를 이용해 스크립트 실행을 지연

### DOM 전체에서 엘리먼트 찾기

옛날 방법 : document.getElementByxxx (live한 컬렉션)
document.getElementById (1개만 찾음 return HTMLElement)

### 이벤트 핸들러 적용

element.addEventListener("click", function(){
this -> element
}, false);

### 이벤트 해제

element.removeEventListener("click", handler, false);
handler의 참조가 있어야지 삭제 가능

### 동적으로 엘리먼트 만들기

* 엘리먼트 생성
* innerHTML

### createxxx

createTextNode(text) : 텍스트 생성
-> body(document.body)에 붙여야함 (appendChild)

### innerHTML

html string을 대입하면 html로 해석해서 자식에 붙여넣음

* 장점 : 보통 빠름, 코드 가독성 좋음
* 단점 : 작은 변화(ex. div 하나 추가)를 주는 경우 비효율적(돔트리를 모두 지우고 다시 만듦) -> 해결 : string을 완성시키고 나서 최종적으로 innerHTML에 대입

### textContent

텍스트 노드를 생성, 참조
특정 엘리먼트의 텍스트 노드를 수정하고 싶을 때 사용
js 코드도 textContent로 출력됨.

### Mozilla developer network

### 함수 표현식

사용하기 전에 함수 생성

### 함수 선언식

선언하고 나서 사용해도 괜찮

### 이벤트 전파

이벤트는 특정한 방향으로 전파된다.
Capturing : 위에서 아래로, 이벤트가 있는지 체크, 있으면 실행 후 밑으로
Bubbling : 아래에서 위로

```
<body>
  <ul>
    <li><input type="checkbox" /> TODO</li>
  </ul>
</body>
```

input checkbox에서 이벤트 발생 (체크)
버블링
li에서 이벤트 발생 (체크 된 것을 다시 체크)
결론 : 작동 안한 것처럼 보임

stopPropagation : 캡처링, 버블링 취소
preventDefault : 기본적인 동작을 취소한다 (ex. 링크 이동 차단)

### CSS

* display : 제일 중요!!! -> 구조에서 없어짐
* id : 1 대 1
* class : 다 대 다 (디자인 적용)

### 엘리먼트 노드
* firstChild
* lastChild
* parentNode
* nextSibling
* previousSibling
* childNodes
