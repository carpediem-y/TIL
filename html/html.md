# HTML
### 0. 학습 목표
html 태그는 외운다기 보다는 사용하면서 익히는 것을 목표로 한다. <br>
새롭게 배우는 점이 있을때마다 추가할 예정이다.
### 1. HTML
Hyper Text Markup Language의 준말로 브라우저에게 콘텐츠의 내용을 보여주는 마크업 언어다.
### 2. 구조
- head: 사이트의 부가적인 정보들을 기록함. 웹사이트에 보여지지 않음
    - title: 브라우저의 title 설정
    - meta: 웹 페이지의 정보와 관련된 태그 <br>
        - ```<meta content = "구글에 표기되는 사이트 설명" name = "description">```: 구글이 검색할 때 찾는 태그
        - ```<meta charset = "utf-8">```: 사이트에서 글자를 읽을 수 있게 해줌. 필수로 입력해야됨!
        - ```<meta property = "og:image">```: 카카오톡에 보여지는 이미지
    - ```<link rel = "shortcut icon" href = "링크">```: 를 통해 사이트 아이콘을 지정할 수 있음.
- body: 화면에 나타나는 내용. html 태그의 대부분이 body에 속함.

### 3. HTML 태그
#### 3-1. 시맨틱 태그
웹 문서 구조를 만드는 태그
- header: 주로 사이트의 위쪽이나 왼쪽에 속함
- nav: 웹 문서 안에서 다른 위치로 연결하거나 다른 웹 문서로 연결하는 링크를 만듦
- main: 핵심 콘텐츠를 담음
- article: 신문이나 기사처럼 실제로 보여주고 싶은 내용이 담김
- section: 콘텐츠 영역 (블로그 포스트처럼 독립된 콘텐츠)
- aside: 본문 외 내용 기록. 필수x
- footer: 맨 아래쪽 영역. 주로 사이트 정보를 담고 있음
- div: 위의 시맨틱 태그가 나오기 전에 사용하던 태그. 현재도 사용함
#### 3-2. 텍스트 관련 태그
- ```<h1>```,```<h2>```,```<h3>```,```<h4>```,```<h5>```,```<h6>```: 제목
- ```<p>```: 길이가 긴 텍스트에 사용
    - ```<abbr>```: 마우스 커서를 대면 나옴 <br>
        ```ex. <p> abbr 사용해보기 <abbr title = "abbr입니다.">마우스를 올려보세요 </abbr>```
    - ```<mark>```: 형광팬 처리 됨
    -  ```<strong>```,```<b>```: 강조
    - ```<em>```,```<i>```: 기울임
    - ```<sub>```: 글자 아래 표기
    - ```<sup>```: 글자 위 표기 (제곱 표기)
- ```<blockquote>```: 인용

- 리스트
    - 순서o: ```<ol>``` <br>
    ```ex) <ol type = " "> 빈 공간에 1,a ...을 지정하면 됨```
    - 순서x: ```<ul>```
- 목록
```
<dl>
    <dt>이름<dt>
    <dd>값<dd>
</dl>
<dt> 태그 안에 여러개의 <dd> 가능
```
#### 3-3. 표 관련 태그
ex.
```
<table>
    <caption>표의 제목</caption>
    <thead>
        <tr>
            <th>thead1</th>
            <th>thead2</th>
        </tr>
    </thead>
    <tbody>
        <!---1행--->
        <tr> 
            <!---열지정--->
            <td>1행 1열</td>
            <td>1행 2열</td>
        </tr>
        <!---2행--->
        <tr>
            <!---열지정--->
            <td>2행 1열</td>
            <td>2행 2열</td>
        </tr>
    </tbody>        
</table>
```
<결과>
<table>
    <caption>표의 제목</caption>
    <thead>
        <tr>
            <th>thead1</th>
            <th>thead2</th>
        </tr>
    </thead>
    <tbody>
        <!---1행--->
        <tr>
            <td>1행 1열</td>
            <td>1행 2열</td>
        </tr>
        <!---2행--->
        <tr>
            <td>2행 1열</td>
            <td>2행 2열</td>
        </tr>
    </tbody>        
</table>

- 합치기
    - ```<td rowspan="합칠 셀 갯수">  (세로 합치기)```
    - ```<td colspan="합칠 셀 갯수">  (가로 합치기)```
    - ```<colgroup>```: 열을 묶어줌. 반드시 caption 태그 다음에 작성!

#### 3-4. 미디어 관련 태그
src를 통해 미디어를 지정해줄 수 있다.
- ```<img>```: 이미지 삽입
- ```<object>```: 다양한 멀티 미디어 파일 삽입
- ```<audio>```: 오디오 삽입
- ```<video>```: 비디오 삽입
- ```<a>```: href 속성을 이용해 하이퍼링크를 만듦

#### 3-5. 폼 관련 태그
- ```<form>```: 폼을 만들어줌
- ```<fieldset>```: 폼의 구역을 나눔
- ```<legend>```: fieldset 태그 안에서 사용되며 fieldset의 제목을 지정함
- ```<label>```: 레이블을 붙일때 사용

<em>fieldset/legend와 label의 차이점 </em><br>
- fieldset/legend 사용
    <form>
        <fieldset>
            <legend>legend</legend>
        </fieldset>
    </form>
- label 사용
    <form>
        <label>label<input type = "text"></label>
    </form>

#### 3-6. 사용자 입력 태그
```<input type = " ">``` type 속성에는  text, email, password 등이 들어갈 수 있다. <br><br>
<em>타입 속성</em>
- ```<radio>```: 라디오 버튼. 1개의 항목 선택 가능. 
- ```<checkbox>```:  체크박스. 1개 이상의 항목 선택 가능. 
- ```<button>```: 기본 버튼. value를 사용해 내용 지정 가능.

input 태그는 label 태그와 함께 사용할 수 있다. <br>
ex.1
```
<label for = "name">이름</label>
<input type = "text" id = "name">
```
<결과><br>
<label for = "name">이름</label>
<input type = "text" id = "name">

ex.2
```
<label>이름<input type = "text" id = "name"></label>
```
<결과><br>
<label>이름<input type = "text" id = "name"></label>

다른 코드로 동일한 결과를 낼 수 있다.

#### 3-7. 그 외 태그
- ```<textarea>```: cols, rows 속성 지정을 통해 여러 줄을 입력할 수 있게 해줌
- ```<select>```, ```<option>```: 드롭 다운 목록을 만들어 줌
- ```<datalist>```, ```<option>```: 데이터 목록을 만들어 줌

### 4. 참고 자료
- [MDN web docs](https://developer.mozilla.org/ko/docs/Web/HTML) <br>
- [노마드 코더 코코아톡 강의](https://nomadcoders.co/kokoa-clone)
<br>
- Do it! 한 권으로 끝내는 웹 기본 교과서 HTML+CSS+자바스크립트 웹 표준의 정석





