---
layout: post
title: 이벤트 리스너(EventListener)
subtitle: 
categories: 자바스크립트(JavaScript)
tags: [자바스크립트,JavaScript]
banner:
image: https://bit.ly/3xTmdUP

---

### practice.html

~~~html
<body>
        
      <div class="box" id="oc">열고닫기창</div>
      <button onclick="열고닫기('block')"> 열기 </button>
      <button onclick="열고닫기('none')"> 닫기 </button>

      <script>
      function 열고닫기(a){
        document.getElementById('oc').style.display = a;
      }
      </script>
  
      </body>
~~~

이벤트 리스너를 사용하여 지난 시간에 했던 본문 부분을 더 간단하게 보여줄 수 있다

다음을 확인해보자

~~~html
<body>
        
      <div class="box" id="oc">열고닫기창</div>
      <button id="open"> 열기 </button>
      <button id="close"> 닫기 </button>

      <script>
     
     document.getElementById('close').addEventListener('click', function(){
       document.getElementById('oc').style.display = 'none'
     });
     document.getElementById('open').addEventListener('click', function(){
       document.getElementById('oc').style.display = 'block'
     });
      
      </script>
  
</body>
~~~

스크립트 부분이 조금 더 길어지긴 했지만, 본문이 짧아져 보기 쉽다.

***

### 이벤트의 종류 
  
- 마우스 이벤트  
  - click : 요소에 마우스를 클릭했을 때  
  - dbclick : 요소에 마우스를 더블클릭했을 때  
  - mouseover : 요소 위로 마우스를 움직였을 때  
  - mouseout : 요소 바깥으로 마우스를 움직였을 때  
  - mousedown : 마우스를 누르고 있을 때  
  - mouseup : 눌렀던 마우스 버튼을 땔 때  
  - mousemove : 마우스를 움직였을 때  
  - contextmenu : 마우스 오른쪽 버튼 눌렀을 때 나오는 메뉴가 나오기 전에 이벤트 발생  

- 키보드 이벤트
  - keydown : 키를 처음 눌렀을 때
  - keyup : 키를 떼었을 때
  - keypress : 키를 누른 상태에서

- UI 이벤트
  - load : 웹 페이지의 로드가 완료되었을 때
  - unload : 웹 페이지가 언로드될 때
  - error : 브라우저가 자바스크립트 오류를 만났거나, 요청한 자원이 없는 경우
  - resize : 브라우저 창 크기를 조정했을 때
  - scroll : 사용자가 페이지를 위아래로 스크롤할 때
  - abort : 이미지의 로딩이 중단되었을 때

- 폼 이벤트
  - input : 인풋 요소 값이 변경되었을 때
  - change : 선택 상자, 체크박스, 라디어 버튼의 상태가 변경되었을 때
  - submit : 사용자가 버튼키를 이용해 폼을 제출할 때
  - reset : 리셋 버튼을 이용할 때
  - cut : 폼 필드의 컨텐츠를 잘라냈을 때
  - copy : 폼 필드의 컨텐츠를 복사했을 때
  - paste : 폼 필드의 컨텐츠를 붙여넣을 때
  - select : 텍스트를 선택했을 때

- 포커스 이벤트
  - focus : 요소가 포커스를 얻었을 때 focusin
  - blur : 포커스를 잃었을 때 focusout

- 드래그 앤 드롭 이벤트
  - dragstart
  - drag
  - dragleave
  - drop


on + '이벤트명' 으로 붙이는 방식도 있지만,
addEventListener로 붙이는 방식이 여러 이벤트도 등록할 수 있고, 특정 이벤트도 제거 가능하는등 장점이 더 많다  
**function()**부분을 콜백(Callback)함수라 하는데, 파라미터로 함수를 전달한다. 그리고 전달받은 그 함수를 함수의 내부에서 실행시킨다.  
즉, 이벤트가 실행됬을 때, 사용자에게 다시 알려주는 기능을 한다.