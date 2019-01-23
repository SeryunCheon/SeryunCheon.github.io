---
layout: post
title:  "로컬프로젝트를 깃허브에 깃(git) push시, [rejected] master -> master (non-fast-forward)에러가 뜰 때"
date:   2019-01-22
excerpt: "열심히 작성한 로컬프로젝트를 깃허브레포지토리에 푸쉬(push)하려 했더니 [rejected] master -> master (non-fast-forward)라는 문구와 함께 푸쉬실패시, 다음과 같이 행동하세요"
tag:
- markdown
- syntax
- sample
- test
- jekyll
comments: true
---
# 깃허브 저장소도 생성하고, 올바른 스텝을 밟았는데?


1) Github에 새 repository를 생성( 깃허브 가입은 안했을시, 미리 가입부터한다.)

2) 생성한 해당 repository에 push할 프로젝트 폴더로 이동한다.( ex, cd 프로젝트명)

3) git init 명령어를 입력, 프로젝트 파일에 .git 폴더를 생성.

4) 모든 파일 staged단계로 추가. (git add .     또는 git add * 명령어 사용)

5) commit 메시지를 작성. git commit -m "메시지내용"


6)  git remote add origin 원격저장소주소 입력

7) git remote push -u origin master (드디어 푸쉬!)

원래 이렇게 하면 정상적으로 푸쉬가 되는게 정상이나 아래와같은 문구, 이미지가 떴다.

![푸쉬거부메시지](./assets/img/githubError.JPG)
 ! [rejected]        master -> master (fetch first)
이 문구가 뜬다.


그럴 때는, 

==git pull origin master --allow-unrelated-histories==
문구를입력해주고, 다시 푸쉬해준다.
(출처: ++https://jwkcp.github.io/2018/03/09/resolving-git-pull-problem/++)

그럼 아래와 같이 정상적으로 Push성공!

![푸쉬거부메시지](./assets/img/githubError2.JPG)




