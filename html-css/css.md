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

1. 컴퓨터 기본 폰트

```
(body 전체 적용, font1이 없다면 2적용, 2가 없다면 3적용 예시)
body {
    font-family: "font1", font2, font3
}
```

2. 사용자 지정 폰트 <br>
   a. 설치한 폰트

```
<style>
@font-face {
    font-family: 'font_name';

    <!--폰트가 있는지 확인하기 위함-->
    src: local('font_name')
}
</style>
```

b. 웹 폰트 (ex.구글)

```
구글 폰트 사이트에 접속해 폰트를 선택한다
➡ + select this style에서 @import문을 선택한다 ➡ style 태그와 font-family를 복사한다.

<style>
    <!--복사한 @import문-->
    @import url('~');
</style>
```
