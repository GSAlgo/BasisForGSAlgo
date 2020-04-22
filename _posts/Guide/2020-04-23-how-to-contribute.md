---
layout: post
title : How to Post
author: Woojin
categories: Guide
tags: [must_read]
---

## 이 문서에 기여하는 방법

### Add Author
/_authors/ 에 자신의 `닉네임.md` 파일을 추가하면 된다. 되도록이면 자신을 잘 나타낼 수 있는 것으로 하자.

양식
```
---
layout: author
name: 닉네임
title: 실명
image: /files/authors/사진 이름
cover: /files/covers/배경 이름
---

소개글
```
사용되는 사진들은 각각 /files/authors/, /files/covers/ 에 넣어주면 된다.

### Add Category (카테고리가 존재하지 않을 경우)
/category/ 에 `카테고리명.md` 파일을 추가한다.

양식
```
---
layout: category
title: 카테고리명
---
```
### Post
/_includes/_posts/카테고리명/ 에 md 파일을 생성한다.  
파일이름은 `yyyy-mm-dd-문서제목.md` 으로 한다. 이때, 제목은 영어로 하며, 공백 대신에 하이픈을 사용한다.

양식
```
---
layout: post
title : 문서제목 (여기에서는 공백을 사용하여도 된다.)
author: 글쓴이 이름(닉네임)
categories: Guide
tags: [태그내용] (태그는 자유롭게 달아주면 된다. 태그 검색 기능은 추가되지 않았다.)
---

내용
```

부가적으로, 포스트에 사진이나 그림이 들어가게될 경우, /assets/images/문서제목/ 에 파일을 넣어준다.


---
## 주의사항 (완전 중요하다)
문서를 다 작성한 후에, 우리는 `pull request`를 통해 관리자에게 게시를 요청하게 된다.
게시를 요청하기 이전에, 자신의 로컬 환경에서 꼭 글을 확인해 본 후에 게시를 요청하도록 하자.
그러지 않는다면, commit을 한 번 더 해야한다.. ~~역시나 귀찮아서이다~~

이 웹사이트는 Ruby의 Jekyll을 기반으로 하기에, 이 두가지를 설치해야 한다.

### 설치

-  Windows 환경

    우선, [RubyInstaller](https://rubyinstaller.org/downloads/)에서 Ruby-Devkit을 설치한다.
    글 작성일 기준으로, stable 버전은 `Ruby+Devkit 2.6.6-1 (x64)`이다. 사이트에 들어가면 진하게 강조되어있는 파일이니 그것을 받아준다.  
    그 후, 설치를 한다. ~~Next만 계속 눌러주자~~ 설치가 끝난 후에, `ridk install`을 실행하여준다.

    이후, 커맨드에 `gem install jekyll bundler` 명령어를 사용하여 Jekyll을 설치한다.

- Ubuntu 환경

    필요로 하는 사람이 있을 경우에 작성하도록 하겠다.

- MacOS 환경

    김재윤에게 물어보자.


### 빌드
로컬에서 사이트를 빌드하기 위해서는, 프로젝트 경로(./GitHub/BasisForGSAlgo/)로 가서 `bundle exec jekyll serve`를 실행한다. 빌드하는데에 약간의 시간이 필요할 수도 있다.

이후, 웹브라우저에서 `http://127.0.0.1:4000/BasisForGSAlgo/`로 가면 자신의 게시글이 반영된 화면을 볼 수 있다. 꼭, 자신의 게시글에 오류가 없는지 점검을 하고 게시를 요청하도록 한다.

**중요**

Gemfile 이 수정되는 경우가 있다. Discard changes를 눌러준 후 자신이 실제로 수정한 파일만 커밋하도록 하자.