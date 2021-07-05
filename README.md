# 플랩풋볼 기술 블로그

플랩풋볼 기술 블로그입니다.



## 환경구성

### project clone

터미널에서 'git clone https://github.com/plabfootball/plabfootball.github.io.git` 명령어를 입력하여 프로젝트를 clone 받습니다.



### Jekyll 설치

터미널에서 'sudo gem install jekyll bunder' 명령어를 입력하여 'jekyll' 과 'bundler'를 설치합니다.

- 윈도우 [windows] (https://jekyllrb.com/docs/installation/windows/)
- 맥OS [macOS] (https://jekyllrb.com/docs/installation/macos/)



### 로컬 환경

터미널에서 프로젝트 경로로 이동한 뒤 아래 명령어를 실행합니다.

```shell
#프로젝트 경로 이동
$ cd plabfootball.github.io
#패키지 설치
$ bundle install
#블로그 서버 실행
$ jekyll serve 혹은 $ bundle exec jekyll serve
```

위 과정에서 오류가 없다면, 브라우저를 열어 [http://127.0.0.1:4000/](http://127.0.0.1:4000/)로 접속 시 로컬에서 블로그가 실행되는 것을 볼 수 있습니다.

#### 환경세팅 완료!

----



## 블로그 포스팅

### 글 작성

- blog 폴더로 이동합니다
- 폴더명은 'YYMMDDHHMM' 포맷으로 생성합니다
- 이미지 첨부가 필요할 경우, 'YYMMDDHHMM' 폴더 내에 'img' 폴더를 생성하고 이미지를 넣어줍니다



### commit & push

- 터미널 에서 프로젝트 root 경로로 이동합니다

```shell
#수정된 파일을 스테이지 리스트에 올립니다
$ git add (--all, .)
#커밋합니다
$ git commit -m "[커밋 메시지]"
#푸시합니다
$ git push -u origin main
```

