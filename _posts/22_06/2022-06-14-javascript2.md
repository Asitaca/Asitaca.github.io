---
layout: post
title: 창 열고 닫기(display, visibility) 및 classList
subtitle: 
categories: 자바스크립트(JavaScript)
tags: [자바스크립트,JavaScript]
banner:
image: https://bit.ly/3xTmdUP

---

## display, visibility

~~~html
<div>1번</div>
<div style="visibility:hidden">2번</div>
<div>3번</div>
~~~

~~~css
div{width:100px;height:100px;background-color: blueviolet;}
~~~

이 html은 아래에 세번째 그림과 같다

<div style="float:left;">
<img src="/assets/images/img/2022_06_15/block.png">
</div>
<div style="float:left;">
<img src="/assets/images/img/2022_06_15/none.png">
</div>
<div style="float:left;">
<img src="/assets/images/img/2022_06_15/visible.png">
</div>  
<br><br><br><br><br><br><br><br><br><br><br>  
<br><br><br>
그림 순서대로    

display: block, visibility: visible  
display: none  
visibility: hidden  

이다.


display: block; 할 경우 창이 보이고  
display: none; 할 경우 창이 보이지 않는다.(공간을 차지하지 않는다.)  

visibility: visible; 할 경우 창이 보이고  
visibility: hidden; 할 경우 창이 보이지 않는다.(공간을차지한다.)

***

### 순서

1. 일단 HTML/CSS로 디자인을 짠다
2. 그 디자인을 열고 닫았다 하는 기능을 구현한다


#### practice.html

~~~html
<!doctype html>
  <html lang="en">
    <head>
      <meta charset="utf-8">
      <title>창 열고 닫기 만들기</title>
      <link href="design.css" rel="stylesheet">
      <!-- design.css 불러오기 -->
    </head>
      <body>
           
      <div class="box" id="oc">열고닫기창</div>
      <button onclick="document.getElementById('oc').style.display = 'block';"> 열기 </button>
      <button onclick="document.getElementById('oc').style.display = 'none';"> 닫기 </button>
         
      </body>
  </html>
~~~

#### design.css

~~~css
.box {
    background-color: black;
    color: white;
    padding: 50px;
    display: block;
  } 
~~~

아래와 같은 그림이 나온다.  

<img src="/assets/images/img/2022_06_15/openclose.png">

'닫기' 버튼을 누르면 검은화면부분이 닫히고,  

'열기' 버튼을 누르면 검은화면부분이 다시 보인다.

~~~html
<body>
        
      <div class="box" id="oc">열고닫기창</div>
      <button onclick="열기()"> 열기 </button>
      <button onclick="닫기()"> 닫기 </button>

      <script>
      function 열기(){
      document.getElementById('oc').style.display = 'block';
      }
      function 닫기(){
      document.getElementById('oc').style.display = 'none';  
      }
      </script>
  
      </body>
~~~

function() 을 활용해 본문을 요약할 수 있다  

function() 안에 들어갈 파라미터는 여러개 사용할 수 있다

더 간략하게 줄일 수 있다

다음과 같다  

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

***

## classList

클래스 추가 삭제를 통하여 다른 방법으로 구현 가능하다.


~~~html
<body>
        
      <div class="box" id="oc">열고닫기창</div>
      <button id="openclose"> 열고닫기 </button>
      
      <script>

     document.getElementById('openclose').addEventListener('click', function(){
       document.getElementById('oc').classList.add('show')
     });
     
      </script>
  
      </body>
~~~

~~~css
.show {
  display: block;
}
~~~

본문 id="oc" 부분에 'show'란 클래스를 추가하였다.  

add - 클래스 추가  

remove - 클래스 제거  

toggle - 클래스가 존재한다면 클래스를 제거하고, 클래스가 존재하지 않는다면 클래스를 추가  

toggle을 사용하면 버튼 한 개로 껐다 켰다를 구현할 수 있다