---
layout: post
comments: true
date: 2020-02-16
title: "15.이벤트 처리_this"
description: "책요약"
category: book
---
<br>

## 이벤트 리스너 안의 this
이벤트 리스너 안의 this는 값을 호출할때 그 함수가 속해 있던 객체의 참조

{% highlight js %}
//예시
window.onload = function () {
  function Person(name) {
    this.name = name;
  }
    Person.prototype.sayHello = function (){
    console.log('hello' + this.name);
  }
  var person = new Person('tom');
  var button = document.getElementById('button');
  button.addEventListener('click',person.sayHello, false);
}
{% endhighlight %}
{% highlight html %}
<body>
  <p>
    <button id="button"> 버튼</button>
  </p>
</body>
{% endhighlight %}

결과는 hello 가 찍힌다 왜냐하면 button에 name 프로퍼티 값이 없기 때문<br>
이처럼 이벤트 리스너 안에 this는 이벤트가 발생한 요소 객체를 가르킨다
<br> 
<br> 
## this가 원하는 객체를 가르키도록 설정하는 법
<strong>bind 메서드 사용</strong><br>
bind 메서드를 사용하면 그 함수가 실행될때의 this를 지정할 수 있다
{% highlight js %}
//예시
window.onload = function () {
  function Person(name) {
    this.name = name;
  }
    Person.prototype.sayHello = function (){
    console.log('hello' + this.name);
  }
  var person = new Person('tom');
  var button = document.getElementById('button');
  button.addEventListener('click',person.sayHello.bind(person), false);
}
//person.sayHello.bind(person)을 추가해주었다
{% endhighlight %}
{% highlight html %}
<body>
  <p>
    <button id="button"> 버튼</button>
  </p>
</body>
{% endhighlight %}

이렇게 바꿔주면 this가 person을 가르키므로 콘솔에는 hellotom 이 찍히게 된다
<br><br>
<strong>익명함수 안에서 실행</strong><br>

{% highlight js %}
//예시
window.onload = function () {
  function Person(name) {
    this.name = name;
  }
    Person.prototype.sayHello = function (){
    console.log('hello' + this.name);
  }
  var person = new Person('tom');
  var button = document.getElementById('button');
  button.addEventListener('click', function(e) {
    person.sayHello();
  },false);
}
//function(e) { person.sayHello();},false);을 추가해주었다
{% endhighlight %}
{% highlight html %}
<body>
  <p>
    <button id="button"> 버튼</button>
  </p>
</body>
{% endhighlight %}

이벤트처리기 또는 이벤트 리스너로 익명함수를 넘기고 익명함수 안에서 메서드를 <br> 
호출하면 그 메서드의 this가 메서드를 참조하는 객체를 가르친다 <br>
결과는 마찬가지!

<br><br>
<strong>화살표 함수 사용</strong><br>

{% highlight js %}
//예시
window.onload = function () {
  function Person(name) {
    this.name = name;
    this.sayHello = () => {
      console.log('hello'+ this.name);
    }
  }
  var person = new Person('tom');
  var button = document.getElementById('button');
  button.addEventListener('click',person.sayHello, false);
  
}
//this.sayHello = () => {console.log('hello'+ this.name);}을 추가해주었다
{% endhighlight %}
{% highlight html %}
<body>
  <p>
    <button id="button"> 버튼</button>
  </p>
</body>
{% endhighlight %}
this는 함수를 초기화 하는 시점에 결정되는데, 이를 활용하여<br>
화살표 함수로 표기하면 그 안의 this가 생성된 객체를 가르킨다
하지만
{% highlight js %}
Person.prototype.sayHello = () => {
  console.log('hello' + this.name);
}
{% endhighlight %}
위와 같은 경우에는 화살표 함수 표현식으로 정의한 함수안의 this가 window객체를 가르킨다