---
layout: post
comments: true
date: 2020-02-16
title: "15.이벤트 처리_addEventListener 메서드, 이벤트 전파 커스텀 이벤트"
description: "책요약"
category: book
---
<br>

## addEventListener 메서드

{% highlight js %} target.addEventListener(type, listener, userCapture) {% endhighlight %}

- <strong>target </strong>: 이벤트 리스너를 등록할 DOM 노드
- <strong>type</strong> : 이벤트 유형을 뜻하는 문자열 ('click', 'mousup' 등)
- <strong>listener</strong>: 이벤트가 발생했을때 처리를 담당하는 콜백 함수의 참조
- <strong>useCapture</strong>: 이벤트 단계 (true-캡처링, false-버블링단계(기본값))

{% highlight js %} //예시
window.onload = function() {
  var element = document.getElementById('box');
  element.addEventListener('click', function(e){
    e.currentTarget.style.backgroundColor = 'red';
  },false)
  // e.currentTarget은 클릭한 요소를 참조하는 요소 객체
  // click -> listener에는 on을 생략하여 대입,
}{% endhighlight %}

<strong>장점</strong><br>
>  같은 요소의 같은 이벤트에 이벤트 리스너 여러개 등록 가능<br>
  DOM 객체에 직접 등록한 이벤트 처리기는 버블링 단계의 이벤트 캡처만 가능<br>
  removeEventListener, stopPropagation, preventDefault를<br> 사용하여 제어 가능

<br>
## removeEventListener 메서드

{% highlight js %} target.removeEventListener(type, listener, userCapture) {% endhighlight %}

- <strong>listener</strong>: 제거할 이벤트

addEventListener의 listener로 익명 함수를 사용했다면 해당이벤트는 삭제 할 수 없다. 
<br>이벤트 리스너 안에서 removeListener를 호출해서 이벤트 리스너가 스스로 삭제하게 만드는 방법이 있다<br>-> (listener에 argument.callee 를 넘기면 된다)//<strong>es5 부터 사용 금지</strong>

<br>
## stopPropagation 메서드
{% highlight js %}event.stopPropagation(){% endhighlight %}
이벤트가 그 다음 요소로 전파되는 것을 막습니다. 

<br>
## stopImmediatePropagion 메서드
{% highlight js %}event.stopImmediatePropagation(){% endhighlight %}
그다음 요소로의 이벤트 전파가 일시적으로 멈춥니다.<br>
또한 그 요소의 객체의 그 이벤트에 등록한 다른 이벤트 리스너도 일시적으로 멈춥니다.

<br>
## preventDefault 메서드
{% highlight js %}event.preventDefault(){% endhighlight %}
a 요소를 클릭하면 링크된 페이지로 이동합니다<br>
이처럼 웹 브라우저에 구현된 기본동작을 취소하기 위해 사용합니다


