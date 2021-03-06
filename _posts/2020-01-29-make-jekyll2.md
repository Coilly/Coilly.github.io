---
layout: post
comments: true
date: 2020-01-29
title: "Github Page Jekyll 시작하기 - 기초세팅"
description: "Github Page Jekyll 만들기 - 기초세팅"
category: jekyll
---
<br>

## git을 이용한 기본세팅 
 
<strong>window 기준으로 된 작성법</strong>이다 (mac을 위한 작성법은 명령어가 다르다)<br>
기본적으로 주 사용 프로그램은 vsstudio와 git을 다룬다.

github 레퍼지스토리(폴더)가 만들어졌으면 git 관리를 위해 자주쓰는 언어 프로그램(저는 vscode)을 사용<br>

![9](https://user-images.githubusercontent.com/37950570/73324299-dfc0d500-428d-11ea-8a81-45e917c0f13e.PNG)
일단 원하는 파일 경로에 들어가 마우스 오른쪽 버튼을 눌러 git bash를 눌러준다<br>

![10](https://user-images.githubusercontent.com/37950570/73324651-06334000-428f-11ea-9eeb-c5dec3da4187.PNG)
git bash를 눌러주면 위의 검은 화면이 뜨는데 여기에 명령어를 쓰면 <br>
github에 있는 repository의 파일들을 가져올 수 있고 수정 등등 다 가능한 창이다<br><br>
이 검은 창(git)에 아래 명령어들을 차례로 친다 ("&nbsp;" 는 제외하고 자신의 것을 넣을것)<br>

{% highlight js %} git config --global user.name "깃허브 네임"
 git config --global user.email "깃허브 이메일" {% endhighlight %}
 
그 다음엔 <code>git config --list</code>를 쳐서 마지막에 나오는 <br>
<code>user.name, user.email</code>이 잘 들어갔는지 확인하기<br>
확인을 다 했다면 vscode를 통해 git 을 가져올 차례다<br><br>

![8](https://user-images.githubusercontent.com/37950570/73323944-8906cb80-428c-11ea-8b6c-86b3c41857c8.PNG)
만들때 보이는 이 http주소를 복사해두고 가져온다<br>
자세한 과정은 [git가져오기 참고](https://demun.github.io/vscode-tutorial/git/)<br>

![12](https://user-images.githubusercontent.com/37950570/73330268-ac894080-42a3-11ea-96be-029d515e0267.PNG)
따라오다 보면 이렇게 원하는 경로에 폴더가 만들어 진다<br>
폴더를 보면 지금은 git 을 이용한 블로그라 .git 의 폴더 밖에 없다 <br>
gitblog page가 잘 만들어 졌는지 확인하기 위해 기본 설정에 들어간다<br><br>

## 화면이 보이기 위한 기본세팅 
 <div class="message"> 
아까 사용한 gitbash 검은창은 vscode에 terminal 역할과 같다
</div>

<br>
terminal을 보이기 위해 저 아래 부분을 눌러준다

![14](https://user-images.githubusercontent.com/37950570/73331068-fbd07080-42a5-11ea-9a2d-8ec4a400ecbd.PNG)
그러면 오른쪽에 터미널이 있는게 보일것이다 이제는 여기에 명령어를 칠 예정이다!

>궁금하지 않을 수 있지만 궁금증이 생길 내용을 하자면<br>
*git 명령어를 (terminal)여기에 쓸거면 처음부터 git 프로그램을 설치 안해도 되는거 아닌가? <br>
-> git 을 기반으로 하는 blog이기 때문에 git 프로그램을 다운받아야 한다.<br>
 쓰는 방법을 알려드렸을 뿐! git 관리는 vscode로 할 예정!<br>


### install ruby 
블로그를 git에 올리기 전에 실행해서 한번 확인하고 마무리될때 올리는게 좋기 때문에<br>
우리는 한번 확인하고 올리는 방법을 해볼 것이다

일단 테마를 다운받기 전에 앞서 git을 설치해 줬으니 이제 ruby, jekyll을 설치해줄 차례다 <br>
[루비 인스톨러 for windows](https://rubyinstaller.org/downloads/)에서 윈도우용 루비 + 개발자킷(DevKit) 설치 프로그램을 다운로드 후 설치한다.<br>
<strong>버전은 최신버전을 다운받았다.</strong>
다운받는 과정은 생략하는데 ,혹시 불안하면 [루비설치](https://blog.tophoon.com/2019/01/12/setup-ruby-for-jekyll.html)를 참고하길!<br>
설치되었는지 확인하기 위해서는 방금 말했던 terminal 에서 <code>ruby-v</code>을 치면 된다

### install bundler
아래의 명령어도 terminal에 치면 된다<br>
아래의 명령어가 무슨 뜻인지 알고 싶다면 자세히 나와있는 [번들러 설치](https://jekyllrb-ko.github.io/tutorials/using-jekyll-with-bundler/)를 참고하기 바란다

{% highlight js %}bundle init
bundle install --path vendor/bundle
bundle add jekyll
bundle exec jekyll new --force --skip-bundle .
bundle install {% endhighlight %}

 <br>

## install bundler
맨 바깥 폴더에 index.html 을 만들어서 안에 hi를 써서 저장한 후 에 아래 명령어를 쳐보자

{% highlight js %}bundle exec jekyll serve {% endhighlight %}

url을 http://localhost:4000/ 쳐서 들어가서, 화면에 hi가 잘나오면 성공이다.
 <br><br>
 
## 테마 적용하기
 
이제 마음에 드는 테마를 골라볼 차례인데,<br>
나는 [layon 테마](https://github.com/poole/lanyon)가 깔끔하고 가독성이 나쁘지 않아서 적용해 보기로 했다

![5](https://user-images.githubusercontent.com/37950570/73321241-3970d180-4285-11ea-86ff-61e649accf0f.PNG)

<br><br>

![6](https://user-images.githubusercontent.com/37950570/73321911-35de4a00-4287-11ea-8b03-f1cca1d1a685.PNG)
테마를 다운받기 위해서는 원하는 git페이지의 화면 오른쪽의 fork 와<br> clone or download 방법이 있는데
fork로 됐을때 바로 적용이 안됐을때도 있어서<br>
<strong> clone or download</strong> 방법으로 진행했다 (fork로 하는 방법은 조금 다르다)
<br><br>

![7](https://user-images.githubusercontent.com/37950570/73322389-0aa82a80-4288-11ea-8075-6432b66480cf.PNG)
zip형식으로 파일을 다운로드 하여 github 블로그가 있는 페이지 폴더에 파일을 압축을 풀고<br>
 아까 hi를 열었던 페이지를 새로고침을 하면 테마가 적용된 화면이 나타날 것 이다. 테마 적용 끝!<br>
 다음시간에는 폴더 구조와 문제점이 담길 예정이다







