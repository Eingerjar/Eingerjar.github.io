---
title: "Git 잔디 심기"
date: 2022-03-10 12:02:32 +0900
categories: TIL
tags: git_commit git git_rebase
---
<img src="https://1.bp.blogspot.com/-01MEhTYvChw/XOXR5UJC8HI/AAAAAAAAKv8/fuHrSz74eswcYlXaicYhX0ozhl7LpfNyQCLcBGAs/s1600/1.JPG" alt="모내기 이미지" style="max-width: 100%; height: auto;">

 github의 잔디를 심으면서 생겼던 문제를 정리했습니다.   
기본적으로 github에 저장소를 다운받아서 `git push`를 하면 정상적으로 잔디가 생기는 것을 확인할 수 있습니다.   
 하지만 만약 다른 컴퓨터에서 접속된 상태에서 `git push`를 해보면 잔디가 안생기는 경우가 있습니다.   
보통 이런 경우는 `git log`를 통해 확인해보면   
```bash
Author: user.name <userID@email.com>
```
해당 작성자와 github에 등록된 작성자가 달라서 생기는 문제입니다. 이를 수정하기 위해서는 `git config`와`git rebase`를 사용해줍니다.   

### git config
작성자의 이름과 이메일을 바꾸기 위해서는 `git config`가 사용됩니다.   
```bash
$ git config --global user.name "github 계정"
$ git config --global user.email "github에 설정된 이메일 주소"
```
해당 저장소에서만 설정하고 싶다면 `--global`옵션을 제거해줍니다.   
위와 같이 설정하면 앞으로 commit을 설정하였을 때 설정된 이름과 이메일이 작성자로 반영되게 됩니다.   
 추가적으로 이름이나 이메일을 잘못입력하였을 경우는 해당 설정을 아래와 같이 입력하여 해당 내용을 삭제하고 다시 설정해줍니다.
```bash
$ git config --unset user.name
$ git config --unset user.email
```
이미 중복되어서 설정해주었다면 `--unset-all`를 사용합니다. 

### git rebase
작성자를 수정하기 위해서 원하는 commit 이전의 commit을 선택합니다.

```bash
$ git rebase -i <commit>
```

해당 커밋을 기준으로 `pick`라고 표시되어 있는 부분 중 수정하고 싶은 커밋을 `edit`으로 바꿔주고 저장해줍니다. 그러면 순서대로 

```bash
$ git commit --amend    //커밋 수정
$ git commit --amend --author="username <useremail@email.com>"
$ git rebase --continue //다음 커밋으로 이동
```
위와 같은 명령어를 참고해서 작성자를 수정해준 후에
```
$ git push -f
```
`-f`옵션을 추가해서 강제적으로 이미 원격저장소에 저장된 커밋로그를 바꿔줍니다.