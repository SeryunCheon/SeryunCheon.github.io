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
feature: https://user-images.githubusercontent.com/30023840/51634455-9f05f000-1f97-11e9-96b5-8b7f034392bd.JPG
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

![githuberror](https://user-images.githubusercontent.com/30023840/51634455-9f05f000-1f97-11e9-96b5-8b7f034392bd.JPG)
 ! [rejected]        master -> master (fetch first)
이 문구가 뜬다.


그럴 때는, 

==git pull origin master --allow-unrelated-histories==
문구를입력해주고, 다시 푸쉬해준다.
(출처: ++https://jwkcp.github.io/2018/03/09/resolving-git-pull-problem/++)

그럼 아래와 같이 정상적으로 Push성공!

![githuberror2](https://user-images.githubusercontent.com/30023840/51634483-afb66600-1f97-11e9-8d48-295dc4b9d6ad.JPG)


### ++또 다른 방법이있다.++

스택오버 플로우에 나와 같은 현상을 겪은 유저가 글을 올렸는데 
좋은 답변들이 달렸기에 공유한다.


**Ask Question**
Is there a good way to explain how to resolve "! [rejected]  master -> master (fetch first)'" in Git?

When I use this command  $ git push origin master it display an error message.

! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:zapnaa/abcappp.git'


답변으로제시한 방법들

1. 
git init<br>git add README.md<br>git add .<br>git commit -m "first commit"<br>git remote add origin https://github.com/userName/repoName.git
여기까진 동일하게 하돼, 아래의 명령어를 입력할것.

		**git push --force origin master**
		(나도 이방법으로 다시한번 해결했다.)

2. **git push origin master --force**<br>or short of force -f<br>**git push origin master -f**


출처: https://stackoverflow.com/questions/28429819/rejected-master-master-fetch-first