---
layout: post
comments: true
date: 2020-01-22
title: "Github Page Jekyll 시작하기 - github만들기"
description: "Github Page Jekyll 만들기 - github만들기"
category: Jekyll
---
<br>

## 개발자에게 편한 블로그?
 작업을 하다보면 제일 좋은 친구는 구글친구가 아닐까 싶다. <br>
 모르는게 있으면 백과사전 급으로 다 알려준다. 하지만 내게 맞는 정확한 지식은  한번에 나오지 않고 알맞게 영문으로 바꾸거나 내용을 더 추가해서 검색해야 한다. 들어가다 보면 분명 일반적인 사이트 같은데 이것 저것 커스텀이 되어있는걸 본적이 있을 것 이다. 개발자들의 블로그는 velog.io, github를 이용한 블로그가 대부분이다. <br>
 근데 나도 초보 개발자(퍼블리셔)니까 .. 블로그를 갖고 싶었다. 메모 어플리케이션을 이용하지만 적당히 메모를 할 뿐이지 
 남에게 알려줄 만큼 정확한 지식을 갖고 있지 않았다. <br>
 이 부분에 대해 안주하기 싫었고, 만들어보기로 했다 
  <br>
  <br>

### 왜 jekyll을 골랐나?

내가 만든것은 github를 이용하여 jekyll(지킬)프레임 워크를 사용한 블로그다.<br>
 각자의 장단점이 있으니 보고 적당한 프레임 워크를 사용하길!
 
  <strong>hexo</strong><br>
  node.js기반이라 속도가 조금 더 빠르지만<br>
   크리에이터가 대만인이라 중국어로 된 내용이 더 많아 
 해석하기 어렵다<br>
  <strong>jekyll</strong><br>
   가장 많은 사용자를 보유하고(한국에서는 많은 것 같다) 영어로 되어있는 내용이 많아<br>
    구글링의 어려움이 덜하고 [github 페이지](https://jekyllrb-ko.github.io/)에 jekyll을 사용한다는 것을 뽑을 수 있겠다 

[내가 jekyll을 고른이유 블로그 참고 1](https://qvil.github.io/blog/why-jekyll/)<br>
[내가 jekyll을 고른이유 블로그 참고 2](http://jihyeleee.com/blog/designer-can-make-jekyll-blog/)<br>
[hexo를 사용해야되는 이유 블로그 참고 1](https://hyunseob.github.io/2016/02/23/start-hexo/)<br>
[hexo를 사용해야되는 이유 블로그 참고 2](https://mingpd.github.io/2019/04/14/github-blog-with-hexo-1/)
  <br>
  <br>

### 기본 블로그
 <div class="message"> 
  일단 만들어진 블로그가 있어서 신규 프로젝트를 추가하여<br>
  다시 만들어보는 시뮬레이션을 거치려고 한다
 </div>
 
  기본적인 jekyll 입문자들에게는 [지킬 기본블로그](https://jekyllrb-ko.github.io/) 처럼 만들어서 실행하라고 나와있다<br>
   하지만 처음코드부터 커멘드라인을 모를수도 있으니<br> [커멘드라인 시작하기](https://tutorial.djangogirls.org/ko/intro_to_command_line/)에 기초 지식을 얻고 작업에 임하길 바란다.
  
     
  *지킬 기본 블로그에 있는 명령어참고
  ![0](https://user-images.githubusercontent.com/37950570/72881352-f625d880-3d43-11ea-9827-862f271b0afb.PNG)
  
  <br>
  
  위의 명령어를 커멘드 라인에 치게 되면 기본 사이트가 나온다
  ![4](https://user-images.githubusercontent.com/37950570/72953970-346dd700-3dda-11ea-8701-22cb0eab58bb.PNG)
   하지만 이 기본 사이트로는 만족이 안되니 괜찮은 테마를 골라서 수정하기로 했다
  <br>  <br>






### github 페이지 만들기
github 페이지에 들어가서 회원가입을 하고 [git](https://git-scm.com/)을 다운받는다<br>
 그리고 github 페이지에서 new repository를 눌러준다.<br>

![1](https://user-images.githubusercontent.com/37950570/72875247-36cb2500-3d37-11ea-8acb-cf1bab4e6b98.PNG)


new repository는 새로운 작업폴더를 만든다는 의미로 여러개 만들어도 상관없다. 

<br>

![2](https://user-images.githubusercontent.com/37950570/72875276-46e30480-3d37-11ea-9188-4cc6083529eb.PNG)

누르면 위의 화면이 뜰텐데, 기본적으로 repository name 은<br>
 <strong>사용자아이디.github.io</strong>으로 짓는게 블로그 사이트의 기본이다.<br>
 나는 기존 블로그가 있고 다시 만드는 중이니 이름을 조금 고쳐서 사용했다
<br>
<br>

![3](https://user-images.githubusercontent.com/37950570/72875292-4cd8e580-3d37-11ea-803a-6e255aa046b1.PNG)
짜잔! 이제 폴더를 만들었고 블로그를 만들 1차 준비가 끝났다!
이제 다음편에는 기본세팅과 원하는 테마를 가지고 오는 부분을 작성하려고 한다
