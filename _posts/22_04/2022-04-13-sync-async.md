---
layout: post
title: 동기(Synchronous) vs 비동기(Asynchronous)
subtitle: 
categories: 개념
tags: [동기,비동기]
---

### 동기처리
자바스크립트의 동기처리란 우선순위 작업이 끝날 때까지 기다리는동안 준비상태가 되기 때문에 다른 작업을 할수가 없습니다.

~~~
console.log("1");
console.log("2");
console.log("3");
~~~

1

2

3

### 비동기처리
자바스크립트의 비동기 처리란 특정 코드의 연산이 끝날 때까지 코드의 실행을 멈추지 않고 다음 코드를 먼저 실행하는 자바스크립트의 특성을 의미합니다. 동시에 여러가지 작업을 처리할 수 있고 기다리는 과정에서 다른 함수를 호출할수도 있습니다.

~~~
console.log("1");
setTimeout(() => {
    console.log("2");
}, 3000);
console.log("3");
~~~

1

3

undefined

2

