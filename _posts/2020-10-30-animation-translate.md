---
layout: post
comments: true
date: 2020-10-30
title: "animation 과 translate 의 성능차이"
description: "animation 과 translate의 차이는 무엇일까"
category: css
---
<br>

## 움직이는 모션을 써야하는데 어느걸쓰지..!?!?(뇌정지)
움직이는 모션을 하려니까 내적 고민이 됐다 translate를 쓸까 animation 쓸까..<br>
옛날 버릇이 여든간다고.. 급한일이 떨어지면 초기에 작업했던 작업물을 찾아<br>
코드를 참고해버리게 된다 (저만 그런가요?)<br> 
처음에 학원에서 배울때는 animation을 주로 쓰곤했다 뭔가 직관적이고 더 잘 떠오르게 되는거 같아서<br>
근데 이 [블로그](https://wit.nts-corp.com/2020/06/05/6134)를 보고나서 animation 보다는 translate 더 권장하게 되었다<br>
블로그에 나와있다시피 animation 과 translate 는 우리가 보기에 동일해 보이지만,<br>
성능 측면에서는 차이가 있다.<strong>translate 은 GPU(GPU는 애니메이션을 처리하는 또 다른 작은 기계,<br>
많은 UI 계산을 처리할 수 있음)를 사용하게 되어 부드러운 렌더링을 할 수 있게 해준다<br>
-> 성능개선은 언제나 옳다 !</strong>

















               
 

