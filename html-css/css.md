# CSS

### 0. 학습 목표

못생긴 html 파일을 css로 꾸며주기!

### 1. 시작

CSS는 Cascading Style Sheets의 준말로
웹 문서에서 스타일을 담당한다.

- html 파일과 연동하는 법
  - 같은 html 파일에 html, css 파일 넣기
  ```
  head파트에 <style> 태그를 추가한다.
  ```
  - css와 html 파일 분리하기
  ```
  html의 head 부분에
  <link href="name.css" rel="stylesheet />
  을 추가한다.
  ```

### 2. CSS

- css의 기본형식:

```
selector { property1: val1; property2: val2; }
```

- css는 위에서부터 아래로 읽기 때문에 같은 선택자를 여러개 작성했을시, 아래의 코드로 적용된다. <br>
  <strong> <mark color: yellow> 다만, 서로 겹치는 속성이 없을 시 모두 적용된다!

#### 2-1. CSS의 선택자

1. `* { ~ }` : 전체 요소에 적용
2. `tagname { ~ }`: 특정 태그를 사용한 모든 요소에 적용
3. `.classname { ~ }`: 특정 클래스를 사용한 모든 요소에 적용
4. `#idname { ~ }`: 특정 아이디를 가진 모든 요소에 적용
5. `selector1, selector2 { ~ }`: 여러 선택자를 묶어 적용

#### 2-2. 스타일 우선순위

<mark>❗ 스타일은 상속된다. body 태그는 웹 문서의 부모 요소임으로 body에 스타일을 지정하게 된다면 자식에게 전부 상속된다.

1. 사용자 스타일 ➡ 제작자 스타일 ➡ 브라우저 기본 스타일
2. !important ➡ inline style ➡ id style ➡ class style ➡ type style

#### 2-3. 폰트 적용하기

a. 컴퓨터 기본 폰트

```
(body 전체 적용, font1이 없다면 2적용, 2가 없다면 3적용 예시)
body {
    font-family: "font1", font2, font3
}
```

b. 사용자 지정 폰트 <br>
ㄱ. 설치한 폰트

```
<style>
@font-face {
    font-family: 'font_name';

    <!--폰트가 있는지 확인하기 위함-->
    src: local('font_name')
}
</style>
```

ㄴ. 웹 폰트 (ex.구글)

```
구글 폰트 사이트에 접속해 폰트를 선택한다
➡ + select this style에서 @import문을 선택한다 ➡ style 태그와 font-family를 복사한다.

<style>
    <!--복사한 @import문-->
    @import url('~');
</style>
```

#### 2-4. 텍스트 관련 style

- text-align: 텍스트 정렬
- line-height: 줄 간격
- text-decoration: 텍스트 줄 표시
- text-shadow: 텍스트 그림자 추가
- text-transform: 대소문자 변환
- letter-spacing, word-spacing: 글자 간격 조정 (자간 조정은 주로 letter-spacing)

#### 2-5. box와 inline

block에는 div, h1, p 등이 있고 inline에는 span, label 등이 있다.

- block은 세로로 정렬된다.
- inline은 가로로 정렬된다.
- block은 높이와 너비를 가질 수 있지만 inline은 가질 수 없다. <br>
  <mark>➡ inline은 padding은 지정할 수 있지만 위, 아래 margin은 가질 수 없다.</mark> <br>
  ~> 만약 inline에 마진을 지정하고 싶다면 display를 사용해 block으로 변경해야 한다.

- box와 콘텐츠 사이의 간격을 margin이라 한다.
- border: 박스의 테두리
- margin: box와 경계 사이 공간
- padding: box와 콘텐츠 사이의 간격

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcI9Fp8%2FbtsEdWFlPKE%2Fiml4WdOGfzLSyVoWKcDGyK%2Fimg.png" width="200" height="200"/>

#### 2-6. Layout

- display 속성을 사용해 inline을 block으로, block을 inline으로 바꿀 수 있다.

```
display: inline-block;
```

을 지정해준다면 inline과 block 요소를 둘 다 가질 수 있게 된다.
하지만 잘 사용하지는 않는다.

- block 요소를 움직이게 하고 싶다면 부모 요소를 flex container로 만들어 주면 된다.

```
ex.
<div>를 움직이고 싶다면 body에 display: flex; 를 지정하면 됨

<style>
  body { display: flex; }
</style>

<body>
  <div></div>
</body>
```

- justify-content는 수평이고, align-items는 수직이다.

```
수평 이동을 하고 싶다면
justify-content: center;

수직 이동을 하고 싶다면
align-items: center;

이런식으로 지정해주면 된다.
```

<mark>justify-content와 align-items를 적용하고 싶다면 display: flex를 먼저 지정해줘야 함!

- flex direction: ~를 추가하면 주축을 바꿀 수 있다. (default: row ↔️ column)

#### 2-7. Pseudo selector

특정 요소 안의 요소를 선택하고자 사용함

```
ex.
<body>
  <p> 어쩌고 저쩌고 <span> 가나다라 </span> </p>
</body>
```

p 태그 안 span 태그를 변경하고 싶을 때 사용

1. 하위 선택자: 부모 자식 {}
2. 바로 아래 선택자: 부모 > 자식 {}
   (1은 손자까지 적용, 2는 자식만)
3. 형제 선택자: 형제1 + 형제2 { }
4. 형제 선택자: 형제1 ~ 형제2 {}
   (3은 형제2의 첫 번째 요소만 적용, 4는 형제2의 모든 요소 적용)

- 특정 속성으로도 지정해줄 수 있다.
  태그 [속성 이름] { } 꼴이다.

- 가상 클래스를 이용해 지정해줄 수 있다.
  (nth-child(), hover 등)
