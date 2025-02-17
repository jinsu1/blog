---
title: "jekyll & MarkDown"
tags:
    - jekyll
    - ruby
    - blog
    - git
    - markdown
date: "2024-07-26"
thumbnail: "/assets/img/thumbnail/jekyll_logo.png"
---
jekyll ,ruby, blog, git, markdown]
## jekyll
### ruby
-ruby 다운로드   
-경로 : [ruby download](https://rubyinstaller.org/downloads/)   
-ruby -v   

### jekyll
-jekyll bundler 설치 (기본경로에 설치) => gem install jekyll bundler   
-jekyll -v   
-bundle init (gemfile 위치 확인)   
-gemfile 위치에서 bundle install   


### Connect & Git & MarkDown
-github에 리포생성   
-원하는 위치에 git clone 받을 폴더 생성    
-생성한 폴더 경로에서 cmd 실행
-git config --global user.name(git계정인증)   
-git config --global user.email

>-git init (깃허브에서 리포를 만들어 clone하지않고 컴퓨터에서 작업을 먼저 시작했을 때 저장소를 생성한다.)   
-git branch -M main   
-git add .   
-git commit -m '커밋내용'   

-git remote add origin 리포주소  

>-git push -u origin main   

-bundle exec jekyll serve 로컬서버 띄우기 (git push없이 바로 변경사항 확인 가능)   
[Markdown문법.PDF](https://github.com/user-attachments/files/16408354/04-.pdf)

### theme
-[jekyll theme download](http://jekyllthemes.org/) 에서 테마 다운로드 후 로컬 폴더에 압축풀기   
-_config.yml에서 url 나의 github url로 변경 (baseurl 수정안 할 시 css가 안먹을 수 있음)   
-baseurl: "/jinsubaji"   
-url: "https://jinsu1.github.io/jinsubaji/"   


### error 
-LF will be replaced by CRLF the next time Git touches it   
 => git config --global core.autocrlf true   

-ruby block in replace_bin_path   
=> gemfile 위치에서 gem bundler install (버전 업그레이드)

-Liquid Exception: Liquid syntax error    
=> 코드블럭 문법 오류 : "{" 중괄호가 연속으로 두 개 들어가면 jekyll에서는 변수로 인식해서 에러가 발생한다. {퍼센트 raw 퍼센트} ... {퍼센트 rawend 퍼센트} 로 감싸주면 정상적으로 build가 진행된다.