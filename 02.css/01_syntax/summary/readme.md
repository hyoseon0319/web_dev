
# CSS

2020-02-14

< file : lab02_font_text.html >

* CSS 폰트와 텍스트

    text-align : right; 
            text-align : left; 

            text-align : center;   

            text-decoration: underline; 

            text-decoration: overline; 

            text-decoration: line-through; 

            text-decoration: none;




< file : lab03_link.html >

* CSS Link

a { } -  선택자 뒤에 : (콜론) 을 붙이고 특정 이벤트마다 적용할 스타일을 설정할 수 있다. 이를 '가상 클래스' 라고 한다.
 
a : hover { } -  hover(호버)는 커서를 해당 요소에 위치 했을 때 스타일을 지정
        
a : active { } - 꾹 누를 때 지정한 색으로 바뀜

a : visited { } - 사이트에 방문했을 때 지정한 색으로 바뀜

a : link { } - 

div : hover { } - div 태그의 hover(호버)는 커서를 해당 요소에 위치 했을 때 스타일을 지정

div : active { } -  



> 배경 색깔 같은 속성을 호버와 액티브에 넣었을 경우, 호버를 위에 배치해줄 것  
     => 액티브 적용된 다음에 호버가 추가 적용 되면서 덮어져 씌워지기 때문



< file : lab04_list_table.html >

* CSS 리스트와 테이블

- ul 태그는 li 태그를 속에 가지고 있음
- ul 태그 ( 부모 태그 ) , li 태그 ( 자식 태그 )

* 상속 : 부모 요소가 가지고 있던 특성들 중에 일부분은 자식 요소에게 전달된다.

CSS 속성- property (프로퍼티)
EX ) CSS 속성을 지정 안해줘도 자동으로 안에 들어가 있는 태그들이 공유


○ - list-style-type: circle;

■ - list-style-type: square;

순서없는 리스트의 모양을 순서로 바꿔줌  :  list-style-type: decimal;

이미지 아이콘으로 바꿔줌 :  list-style-image: url(https://cdn0.iconfinder.com/data/icons/iconsweets2/40/whale.png); - 크기 조정이 끝난 이미지를 써야함

o { } -

            list-style-type: lower-alpha;
            list-style-type: disc;

.shortHand { } -
            list-style: circle;
