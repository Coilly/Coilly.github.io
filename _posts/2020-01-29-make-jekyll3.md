---
layout: post
comments: true
date: 2020-01-30
title: "Github Page Jekyll 시작하기 - 폴더 구조 파악"
description: "Github Page Jekyll 만들기 - 폴더 구조 파악"
category: jekyll
---
<br>

## 문제가 생겼다
테마를 다 적용했는데 문제가 생겼다.<br> 이 문제점에 해당되지 않는다면 넘겨도 좋다

<strong>문제점 1 - bundle exec jekyll serve 에러</strong>

전 글에서 아래 명령어를 치면 localhost:4000이 생성된다고 말했었다.<br>
{% highlight js %}bundle exec jekyll serve {% endhighlight %}

이 명령어를 쳤는데 아래의 글들이 나오면서 만들어지지 않고 있었다 <br>


 {% highlight js %}
 Since v3.0, permalinks for pages in subfolders must be relative to the site source directory, not the parent directory. Check https://jekyllrb.com/docs/upgrading/ for more info. 
------------------------------------------------ 
Jekyll 4.0.0   Please append `--trace` to the `serve` command 
for any additional information or backtrace. 
------------------------------------------------{% endhighlight %}
                     
글을 잘 읽어보니 permalinks 가 문제인거 같았다.<br>
일단 지금 실행중이던 terminal을 중지하고 (ctrl + c , y 연타)  원인을 알아보니 plugin 문제였다<br>
                       
![18](https://user-images.githubusercontent.com/37950570/73423064-61882f80-436e-11ea-9082-3ca420815202.PNG)
일단 _config.yml파일 여기에 밑줄친 부분을 지우고<br>

<div class="message">
<strong>_config.yml 파일에 아래를 추가<br></strong>
plugins:<br>
  - jekyll-paginate<br>
paginate: 5<br><br>

<strong>Gemfile 파일에 아래를 추가<br></strong>
group :jekyll_plugins do<br>
   gem "jekyll-paginate"<br>
end
</div>
그 다음에 명령어에 bundle install 을 치고 다시 localhost를 실행하는 <code>gem install jekyll-paginate</code>을 쳤다. 드디어 고쳐졌다!<br><br>
                     
## 이제 폴더구조 파악

기본적인 폴더 구조는 [jekyll공식사이트](https://jekyllrb-ko.github.io/docs/structure/)를 기준으로 한다 한번 읽으면서 파악할 것.<br>
.bundle , .git, .jekyll-cache, vendor 은 환경설정에 관한 것이고 gemfile, gemfile.lock은 ruby에 대한 환결설정 쯤으로 이해하면 될것 같다 
![19](https://user-images.githubusercontent.com/37950570/73435703-812e5080-438c-11ea-893a-e0b031c3b57c.PNG)

여기서 중요한건<strong> __includes, __layouts, __posts, __site, _config.yml</strong>를 꼽을 수 있다<br>
왼쪽에 slide-bar은 블로그의 상태를 나타내는 _config.yml 안을 수정하면 된다





               
 

