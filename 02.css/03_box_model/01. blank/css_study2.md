# CSS

## 1-1 CSS란?
#### - CSS (Cascading Style Sheet) : html 문서에 색이나 모양, 출력 위치 등 외관을 꾸미는 언어
- **CSS 속성 : property**
   - CSS 속성을 지정 안해줘도 자동으로 안에 들어가 있는 태그들이 공유
- **CSS 문법**
   - 항상 ; (세미콜론)으로 끝나야 함
   - CSS 특징 상 속성명에 스페이스가 끼지 않음 ( 하이픈 ' ' 을 쓰는 이유 )
- **CSS의 위치**
   - `<head>` 요소 내에서 `<style>...</style>`안에 적어줌 (내부 스타일 시트 적용)

> ※ CSS의 장점
> 1) 유지보수가 편함
> 2) 재사용성이 높음 (이미 적용된 것을 복붙)

## 1-2 CSS 스타일 시트 구성 

#### 스타일 시트 (style sheet) : css로 작성된 코드 
- 선택자와 같은 이름의 모든 HTML 태그에 스타일 시트가 적용됨
```
선택자(selector) {프로퍼티(property):값(value); (; 는 구분자)}
```
- 스타일 시트 블록 : **중괄호 { }** 이용
- **프로퍼티 : 값 ;** (CSS는 약 200개 프로퍼티가 있음) 
> => 여러 개의 프로퍼티를 넣어주고 싶으면 ; 으로 구분해주면 됨 ( 구분자 )
- 주석 :  /* ..  */
- 대소문자 구분 없음 (선택자, 프로퍼티, 값)

```
span { color : blue; font-size : 20px; } /* span 태그 스타일 선언 */
  ex) span 셀렉터에 의해 html 페이지의 모든 <span> 태그에 'color:blue; font-size : 20px' 의 스타일이 적용됨
```

### <선택자>
: CSS3 스타일 시트의 이름이나 규칙
- html 요소를 선택해서 우리가 원하는 스타일을 적용시키기 위해서는 **선택자** 사용이 중요 !

* 적용순서: 인라인스타일 > 아이디선택자 > 클래스선택자 > 태그선택자

1. 태그 선택자 ( 태그 이름 ) 
2. 전체 선택자 ( * ) 
   - 페이지 안 모든 요소에 공통적인 속성 지정
3. ID 선택자 ( # ) 
   - 특정한 요소를 쉽게 선택 가능   
4. 클래스 선택자 ( . )
   - 몇 개의 요소를 하나의 클래스로 묶어서 스타일 지정
5. 그룹 선택자 ( h1, h2, h3 )
   - 동일한 규칙을 가지는 선언을 하나로 축약가능
6. 속성 선택자 ( input [ type=text ] { color : red ; } )
   - type 속성값이 "text"인 `<input>` 태그에 적용
7. 가상 클래스 선택자 ( **:visited , :hover** )

8. 선택자 조합
   - 자식 선택자
   - 자손 선택자
   
#### 적용:인라인스타일>아이디선택자>클래스선택자>태그선택자 

```
a:visited { color : green; }   // 방문한 후부터 <a>의 링크 텍스트 색을 green으로 출력
li:hover { background : yello; } // <li> 태그 위에 마우스가 올라오면, yellow를 배경색으로 출력

a{ } -  선택자 뒤에 : (콜론) 을 붙이고 특정 이벤트마다 적용할 스타일을 설정할 수 있다. 이를 '가상 클래스' 라고 한다.
a:hover { } -  hover(호버)는 커서를 해당 요소에 위치 했을 때 스타일을 지정
a:active { } - 꾹 누를 때 지정한 색으로 바뀜
a:visited { } - 사이트에 방문했을 때 지정한 색으로 바뀜


tip★ 배경 색깔 같은 속성을 호버와 액티브에 넣었을 경우, 호버를 위에 배치해줄 것  
     => 액티브 적용된 다음에 호버가 추가 적용 되면서 덮어져 씌워지기 때문
```

####  ※ ID 선택자 - Class 선택자 차이점
- ID 선택자 : 하나의 요소만 선택 ( 기본키, UNIQUE값 같은 역할 )
   => ID는 두 개 이상 적용되기도 함
- 클래스 선택자 : 여러 개의 요소를 한꺼번에 선택

```
순서를 다 무시하고 싶을 경우 : 

!important
      ex) .class { color: blue !important; }

CSS는 같은 속성을 여러 번 정의했을 때, 나중에 설정한 값이 적용됨
만약 나중에 설정한 값이 적용되지 않게 하려면 속성값 뒤에 !important를 붙임

------------------------------------------------------------------------------------------

* 클래스 선택자 :
클래스 내부의 순서가 아닌 클래스를 먼저 쓰는 순서가 중요  
스타일 시트 상에서 스타일 태그 내에서 내가 적용하고자 하는 클래스가 가장 마지막에 있는지가 중요!

```       
## 1-3 CSS 시트 작성 3가지 ( HTML 문서 )
1. 인라인 스타일 : (추천 안함)
    - **선택자 필요 없음★**
    - style 속성에 스타일 시트 작성

```
 * 인라인 요소의 ‘인라인’ : 영역 지정해서 속성을 넣어주고 꾸며주는 것
    - 인라인 스타일도 똑같음 ( 가장 강한 우선 순위 )
    - 스타일 속성에 붙은 태그 하나만 꾸며줌

      ※ 단점 : 찾기 힘듦, 수정이 어려움
```

2. 임베딩 스타일 (내부 스타일 시트)
   - `<style></style>` 태그에 스타일 시트 작성
   - CSS 속성이 HTML 파일 내부에 있음   

3. 링크 스타일 (외부 스타일 시트)
   - 스타일 시트를 .css 파일로 작성하고, `<link>` 태그나 @import로 분리 사용
```
    ***링크 스타일을  추천하는 이유!**  
   - link 종료 태그가 없음
   - 중복 작성 불편함 해소
   - 웹 사이트의 전체 웹 페이지 모양에 일관성 줌
```
<link type= "text/css" rel="stylesheet" href = "mystyle.css">

=> text/css : css 언어로 작성된 텍스트 파일
=> rel : 불러오는 파일이 stylesheet
=> href : mystyle.css 파일을 불러옴 ( 다른 웹 사이트에 있는 경우, 웹 사이트의 URL을 기입 
    ex) href="http://www.site.com/mystyle.css" )


```
@ import 이용

<style>
    @import url(mystyle.css);
</style>

=> <style> 안에서만 사용됨
```

- `<style>` 태그는 반드시 `<head>` 태그 내에서만 작성 가능
- `<style>` 태그는 여러 번 작성 가능 ( 스타일 시트들이 합쳐 적용됨 )
- `<style>` 태그에 작성된 스타일 시트는 웹 페이지 전체에서 적용됨

## 1-4 CSS 규칙

- CSS3 스타일은 부모 태그로부터 상속됨
- 스타일 합치기(cascading) 
  - 태그에 적용되는 모든 스타일이 합쳐짐


- 오버라이딩(overriding) : 덮어쓰기
   - 동일한 스타일은 우선순위를 따름 


## 1-5 색, 텍스트, 폰트
#### 색
- CSS 에서 색은 RGB, RGBS, HSL
```
style = "color:red;" : 컬러명
style="color:rgb(red,green,blue)" : rgb값
style="color: #ff0000;" : hex(=16진수) / 2글자씩 각각 r,g,b를 뜻함
```

#### 텍스트
- CSS3로 들여쓰기(text-indent), 정렬(text-align), 텍스트 꾸미기(text-decoration) 가능
- CSS 폰트와 텍스트
```
text-indent  length; /* 고정된 길이 */
text-indent  percentage; /* 텍스트 블록 전체 폭에 대한 비율로 들여쓰기 */
 text-align : right;  /* 오른쪽 정렬 */
text-align : left;   /* 왼쪽 정렬 */
text-align : center;  /* 중앙 정렬 */
text-align : justify;  /* 양쪽 정렬 */
text-decoration: underline; /* 밑줄 */
text-decoration: overline; /* 윗줄 */
text-decoration: line-through; /* 중간 줄 */ 
text-decoration: none; /* 밑줄 없음 */
```
#### 폰트

```
font-family : 폰트체 이름 
font-size : 폰트 크기(px, em)
font-style : normal , italic , oblique
font-weight : 폰트 굵기 (bold, strong)
font : font-style font-weight font-size font-family : 폰트 단축 프로퍼티

ex) font-size, font-family 는 반드시 지정되어야함 !
    20픽셀로 이탤릭 스타일에 bold 굵기의 consolas체
    font : italic bold 20px consolas, sans-serif; 
```

px : 상위요소에 영향을 받지 않는 고정적인 크기
em : 부모요소에서 지정한 크기를 기준으로 배율 조정

-  글자 크기를 유동적으로 변경해야하는 작업을 할 때 많이 사용함 (rem과 같이) 
> ex) 부모요소 font-size 16px 이라면 div 요소의 fontsize가 2em 일 때 이 단위의 px크기는 32px

rem : root em
- html 문서의 기본인 html 요소 크기를 기준으로 배율 조정


## 1-6 박스 모델

CSS3 -> contents(내용), padding, border, margin으로 구성된 사각형 박스를 다룸

#### 박스의 구성
콘텐츠 : html 태그의 텍스트나 이미지 부분
padding : 콘텐츠를 직접 둘러싸고 있는 내부 여백
border : padding 외부의 외곽선으로 직선이나 점선 혹은 이미지로 입힐 수 있음
margin(여백) : 박스의 맨 바깥 영역, 테두리 바깥 공간으로 아래위 인접한 태그와 만나는 공간


![image](http://blogfiles.naver.net/MjAxOTA4MTVfMjA0/MDAxNTY1ODU3NjU0ODA1.vg7VR5q78rZVFDdlIUcxVBwe4m8Du67l9-O81Od2Bhsg.6pAaftk3NTiBarBSNlAco4pQ7xvApxqI5LpDHDk9B0Ig.JPEG.juyoung1704/28.jpg)

#### 박스 프로퍼티
**박스의 크기 제어**
width (가로 폭) , height (세로 폭) , margin (여백), padding

  | contents | padding | border | margin |
  |---|:---:|---:|---:
`크기` | width, height | padding-top, padding-right, padding-bottom, padding-left|border-top-width, border-right-width, border-bottom-width, border-left-width | margin-top, margin-right, margin-bottom, margin-left 
`크기 단축` | - | padding | border-width | margin
`스타일` | - | - | border-top-style, border-right-style, border-bottom-style, border-left-style | - 
`스타일 단축` |  | - | border-style | -  
`색` | - | 패딩의 색은 따로 없음, 태그의 배경색으로 칠해짐 | border-top-color, border-right-color, border-bottom-color, border-left-color | 여백은 투명, 부모 태그의 배경이 비춰보임  
`색 단축` | - | - | border-color | -
`전체 단축` | - | - | border | - 

>border-box : 마진을 제외한 박스 모델 전체를 width, height 프로퍼티의 대상 영역으로 지정 (직관적 사용)

```
<p class="individual">방향 하나씩 적용</p>
<p class="shorthand">축약형</p>
<p class="auto">좌우 동일하게 정렬 (위아래 적용x)</p>

* 축약 표현법 
테두리의 축약 표현시에는 반드시 border-style 속성이 먼저 설정되어 있어야 제대로 표현 
* radius 적용
border-radius를 적용할 경우, 해당 요소의 이미지, 배경 관련 요소들이 모두 잘려서 표현
```
### 배경
- HTML 태그에 배경색을 칠하거나 배경 이미지를 출력하는 방법
```
background-color : 배경색 지정
background-image : 배경 이미지 지정 
- url("media/spongebob.png");
- linear-gradient(45deg,#feda75,#fa7e1e,#d62976, #962fbf, #4f5bd5); ex) 인스타그램
- 방향 : __deg , to top left (bottom, right 등등)


background-position : 배경 이미지의 위치 left top(디폴트)
background-size : 배경 이미지의 크기 , 값 contain, cover, px, %   ex) 100px 100px

background-repeat : 배경 이미지 반복 출력 repeat(디폴트)
background color image position/size repeat orgin: 단축 프로퍼티
=> background 프로퍼티에는 배경색이나 배경 이미지만 지정 가능 

```
```
contain: 짧은 면을 기준으로 사이즈 변경 (이미지가 다 보이게)
cover: 긴 면을 기준으로 사이즈 변경 (사진 잘릴 수 있음)

%: 출력되는 이미지에서 차지하는 비율
ex) 50% 지정해주면 이미지가 2장만 나옴(20%면 5장의 이미지 출력 - 왓챠) 
```
## 1-7 CSS 리스트와 테이블

- ul 태그는 li 태그를 속에 가지고 있음
- ul 태그 ( 부모 태그 ) , li 태그 ( 자식 태그 )

* 상속 : 부모 요소가 가지고 있던 특성들 중에 일부분은 자식 요소에게 전달된다.

***tip***. CSS 로 표의 테두리를 설정 할 때 표의 바깥 테두리와 셀의 테두리를 따로 지정해야함

```
HTML
<table class="table1">
   <tr>
      <th>속성 값</th>
      <th>설명</th>
   </tr>
   <tr>
      <td>top</td>
      <td>캡션을 표의 윗부분에</td>
   </tr>
   <tr>
      <td>bottom</td>
      <td>캡션을 표의 아랫부분에</td>
   </tr> 

CSS
.table1{
   border:1px solid black;
}.table1 th{
   border:1px dotted black;
   padding:10px;
}.table1 td{
   boder:1px dotted black;
   padding:10px;
}
```



### 리스트 스타일 속성

list-style-type: none; // 아무런 장식 보여주지 않음 

**1. ul 요소에 어울리는 값**

list-style-type: disc; // ●  (ul 요소의 기본 값)
list-style-type: circle; // ○
list-style-type: square; // ■ 

**2. ol 요소에 어울리는 값**

list-style-type: decimal; // 숫자 1.2.3.
  => 순서없는 리스트의 모양을 순서로 바꿔줌 

list-style-image: url(https://cdn0.iconfinder.com/data/icons/iconsweets2/40/whale.png);  // 이미지 아이콘으로 바꿔줌 
***tip*** 크기 조정이 끝난 이미지를 써야함

list-style-type: lower-alpha; // 소문자 a,b,c
list-style-type: upper-alpha; // 대문자 A,B,C 

```
* caption-side 속성- 표 제목 위치 정하기
caption-side:top|bottom
--------------------------------------------------------------------------------------------------------
* border 속성- 표 테두리 스타일 설정
1px solid gray; // 외곽선 설정. 값은 굵기, 특성, 색상 
solid = 실선
--------------------------------------------------------------------------------------------------------
* border-collapse 속성 - 테두리 통합, 분리
border-collapse:separate; 기본값 (따로 표시)
border-collapse: collapse;
테이블 셀들을 합쳐서 공백 없앰, 테두리도 합쳐짐 
tip★ only <table> 요소에서만 사용가능
--------------------------------------------------------------------------------------------------------
* border-spacing 속성 - 인접한 셀 테두리 사이 거리 지정
border-spacing:<크기>;
px나 em 등 크기와 단위를 직접 지정 
(값이 1개 수평거리와 수직거리 한거번에 지정, 2개 <수평거리><수직거리>)
--------------------------------------------------------------------------------------------------------
* empty-cells 속성 - 빈 셀의 표시 여부 지정
empty-cells: show|hide
show: 빈 셀 주위에 테두리를 그려 빈 셀 표시
hide: 빈 셀에 테두리를 그리지 않고 비워둠
tip★ only <table> 요소에서만 사용가능
--------------------------------------------------------------------------------------------------------
* width, height 속성 - 표 너비와 높이 지정
width: <크기>; height: <크기>;
td 선택자에 적용 시, 그 데이터의 영역 크기 변경 가능
조정하지 않으면 셀 안의 내용이 표시될 만큼만 표시되거나 내용이 없을 시 보기 흉하게 나옴
ex) <크기> : px와 부모요소를 따라가는 %
--------------------------------------------------------------------------------------------------------
* 크기 조정
width:__px; height:__px; // 픽셀을 기준으로 하는 절대적 크기
width:__%; height:__%; // %를 통한 크기 조정
> 퍼센트 속성은 가로는 적용되지만 세로가 안될 때가 있음 
      => 부모 요소가 아무런 길이를 갖고 있지 않은 경우 !
--------------------------------------------------------------------------------------------------------
* table-layout 속성 - 콘텐츠에 맞게 셀 너비 지정
table-layout:fixed; // 글자가 튀어나갈수도
auto : 기본 값 ( 셀 내용에 따라 너비 달라짐 )
fixed : 셀 너비 고정
tip★ 셀 너비를 고정한 상태에서 셀 너비 안에 셀 내용을 표시 하려면 ?
word-break:break-all 속성, height 속성도 auto로 지정 (줄 바꿈이 생기면 높이 값도 바뀌기 때문에 )
--------------------------------------------------------------------------------------------------------
* text-align 속성 - 셀 안에서 수평 정렬
text-align : left|right|center
--------------------------------------------------------------------------------------------------------
* vertical-align 속성 - 셀 안에서 수직 정렬
inline이나 inline-block 으로 배치한 요소의 세로 정렬 방법을 지정
vertical-align:baseline|top|bottom|middle|sub|super|text-top|text-bottom|<길이 값>|<백분율 값>
```

### CSS Display
- 웹 페이지의 레이아웃을 결정하는 css의 중요한 속성
- html 요소가 웹 브라우저에서 언제 어떻게 보이는가를 설정
  ex) inline, block, inline-block
```
1. 블록 ( div, p )
   display 속성값이 block인 요소는 언제나 새로운 라인에서 시작, 해당 라인의 모든 너비를 차지

2. 인라인 ( span, a )
   display 속성값이 inline인 요소는 새로운 라인에서 시작하지 않음
   해당 html 요소의 내용만큼만 차지   
```

**display 속성의 기본 설정값의 변경**
1. display:block; // 인라인 요소를 블럭요소로 변경
 => block 요소로 변경 할 경우 상하의 높이, 여백을 줄 수 있음

2. display:inline; // 블럭요소를 인라인 요소로 변경 
 => 쓰는 경우가 별로 없음
