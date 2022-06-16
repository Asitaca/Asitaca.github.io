---
layout: post
title: getElement, querySelector
subtitle: 
categories: 자바스크립트(JavaScript)
tags: [자바스크립트,JavaScript]
banner:
image: https://bit.ly/3xTmdUP

---
| getElementById | ID |
| getElementsByClassName | class |
| getElementsByTagName | Tag |
| getElementsByName | name |
| querySelector | 선택자 |
| querySelectorAll | 선택자 |

***

### getElementById, getElementsByClassName, getElementsByTagName, getElementsByName

~~~html
<h1 id="hi">반갑습니다</h1>

<script>
  document.getElementById('hi').innerHTML = '안녕';
</script> 
~~~

'id' 가 'hi'인 부분을 찾아서 '반갑습니다'를 <span style="color:red">'안녕'</span> 으로 변경해준다

***

~~~html
<h1 class="hi">반갑습니다</h1>
<h1 class="hi">안녕</h1>
<h1 class="hi">잘가</h1>



<script>
  document.getElementsByClassName('hi')[0].innerHTML = '안녕';
</script> 
~~~

찾고자 하는 요소가 중복될 때 차례대로 [0],[1],[2]... 순서를 붙여 찾을 수 있다.  
뒤에 숫자를 붙이지 않고 찾게 되면 맨 처음에 있는 요소를 찾는다. 
ID의 경우 유니크해야하므로 중복되서도 안되고 중복된다 해도 이 방법을 사용할 수 없다.

***

~~~html
<script>
document.getElementById('hello')[0].style.color = 'red'; 
//칼라 변경
document.getElementsByClassName('hello')[0].style.fontSize = '20px';
//폰트사이즈 변경
</script>
~~~

이런식으로 css부분도 변경할 수 있다.

***

### querySelector, querySelectorAll

~~~html
<h1 class="hello">이건 첫번째 클래스!</h1>
<h1 id="hello">이건 아이디!</h1>
<h1 class="hello">이건 두번째 클래스!</h1>


<script>

  document.querySelector('.hello').innerHTML = '안녕';
  //찾게될 요소가 클래스일 경우 요소 앞에 '.' 을 붙인다
  document.querySelector('#hello').innerHTML = '안녕';
  //찾게될 요소가 아이디일 경우 요소 앞에 '#' 을 붙인다
  document.querySelector('h1').innerHTML = '안녕';
  //찾게될 요소가 태그일 경우 요소 아무것도 붙이지 않는다
  document.querySelectorAll('.hello')[1].innerHTML = '잘가';
  //요소가 중복될 경우 뒤에 숫자를 붙여 찾을 수 있다

</script> 
~~~

querySelector는 본문의 가장 첫 번째 요소를 찾을 수 있고,    
querySelectorAll는 찾고자 하는 요소가 중복될 때 차례대로 [0],[1],[2]... 순서를 붙여 찾을 수 있다.  

