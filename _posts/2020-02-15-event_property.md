---
layout: post
comments: true
date: 2020-02-16
title: "15.이벤트 처리_이벤트객체, 키보드, 마우스 이벤트"
description: "책요약"
category: book
---
<br>

## 공통 프로퍼티

<strong>1. 이벤트 객체의 공통 프로퍼티</strong>

| 프로퍼티 | 값의 타입 | 설명 |
| :-| :- | :- |
| type | 문자열 | 이벤트 이름(click, mousedown, <br>keydown 등) |
| target | 요소객체 | 이벤트가 발생한 요소 |
| currentTarget | 요소객체 | 처리를 담당하는 이벤트 리스너가<br> 등록된 요소 객체 |
| eventPhase | 정수 | 이벤트 전파단계 <br>(1: 캡쳐링 2: 타깃 3: 버블링) |
| timeStamp | 정수 | 이벤트 발생 시각 |
| bubbles | 논리값 | 버블링 단계인지를 뜻하는 값 |
| canclelabel | 논리값 | preventDefault()로 기본 이벤트를 <br>취소 할 수 있는지를 뜻하는 값 |
| defaultPrevented | 논리값 | preventDefault()로 기본 작업이<br> 취소 되었는지를 뜻하는 값 |

<strong>2. 마우스와 관련된 이벤트가 가진 프로퍼티</strong><br>
대표적인 이벤트는 click, dbclick, mouseup, mousemove, mouseout, mouseover

| 프로퍼티 | 값의 타입 | 설명 |
| :-| :- | :- |
| screenX, screenY | 정수 | 클릭한 위치의 화면 좌표<br>(컴퓨터 화면의 왼쪽 위 꼭짓점이 원점) |
| clientX, clientY | 정수 | 클릭한 위치의 윈도우 좌표<br>(표시영역의 왼쪽 위 꼭짓점이 원점) |
| pageX,  pageY | 정수 | 클릭한 위치의 문서좌표<br>(문서의 왼쪽 위 꼭짓점이 원점) |
| offsetX, offsetY | 정수 | 이벤트가 발생한 요소의 상대좌표<br>(요소의 왼쪽 위 꼭지점이 원점) |
| altKey | 논리값 | alt가 눌렸는지 뜻하는 논리값 |
| ctrlKey | 논리값 | ctrl가 눌렸는지 뜻하는 논리값 |
| shiftKey | 논리값 | shift가 눌렸는지 뜻하는 논리값 |
| detail | 정수 | 이벤트의 자세한 정보 <br> 마우스 이벤트의 경우에는 클릭한 횟수 |
| button | 정수 | 눌린 마우스의 버튼 <br>(0:왼쪽버튼 1: 휠버튼 2:오른쪽버튼) |
| relatedTarget | 객체 | mouseover 이벤트에서는 마우스가 떠난 노드 <br>mouseout 이벤트에서는 마우스가 들어온 노드 |

{% highlight js %}
//box를 누르고 떼면 그자리에 위치해 주는 예시
function elt(name, attribute) {
    //element name 을 넣고 ,값을 넣으면 만들어지는 function
    var node = document.createElement(name);
    if(attribute){
        for(var attr in attributes) {
            if(attreibutes.hasOwnProperty(attr)){
                node.setAttribute(attr, attributes[attr]);
            }
        }
    }
    for(var i=2; i< arguments.length; i++) {
        var child = arguments[i];
        if(typeof child == 'string') {
            child = document.createTextNode(child);
        }
        node.appendChild(child);
    }
    return node;
}
window.onload = function (){
    var box = elt('div',null, 'javascript');
    document.body.appendChild(box);
    var boxOffsetX, boxOffsetY;
    box.style.display ="inline-block";
    box.style.position= "absolute";
    box.style.padding="10px";
    box.style.backgroundColor = "blue";
    box.style.color ="white";
    box.style.cursor ="pointer";
    box.addEventListener('mousedown', function mouseDownListener(e){
        document.addEventListener('mousemove', mouseMoveListener, false);
        boxOffsetX = e.offsetX;
        boxOffsetY = e.offsetY;
    
    },false)
    document.addEventListener('mouseup', function mouseUpListener(e){
        document.removeEventListener('mousemove', mouseMoveListener, false);
    
    },false);
    function mouseMoveListener(e) {
        box.style.left = e.pageX - boxOffsetX + 'px';
        box.style.top = e.pageY - boxOffsetY + 'px'
    }
}
 {% endhighlight %}

<strong>3. 키보드와 관련된 이벤트가 가진 프로퍼티</strong><br>
대표적인 이벤트로는 keydown, keypress, keyup

| 프로퍼티 | 값의 타입 | 설명 |
| :-| :- | :- |
| altKey | 논리값 | alt가 눌렸는지 |
| ctrlKey | 논리값 | ctrl가 눌렸는지 |
| shiftKey | 논리값 | shift가 눌렸는지 |
| metaKey | 논리값 | Meta가 눌렸는지 뜻하는 논리값<br>(맥은 command, 윈도우는 윈도우 버튼) |
| key | 문자열 | 눌린 키의 DOMString |
| keyCode | 정수 | 눌린 키의 키 코드 |
| code | 문자열 | 눌린 키가 키보드에서 차지하는 물리적 위치를 뜻함 |


