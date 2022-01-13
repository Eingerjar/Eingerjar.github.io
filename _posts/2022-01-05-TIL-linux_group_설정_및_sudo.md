---
title: "linux group 설정 및 sudo"
date: 2022-01-05 13:58:21 +0900
categories: TIL
tags: Linux_group group sudo
---

## Llinux group 설정

그룹에 유저를 추가하기 전에 먼저 유저를 어떻게 하는 지 알아보겠습니다.<br>

### 유저 추가하기

```bash
adduser [username]
```

유저 이름을 입력하게 되면 비밀번호와 아래와 같은 정보를 물어보게 되는 데 모두 옵션이기 때문에 넘어 가셔도 됩니다.<br>

```bash
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
Changing the user information for username
Enter the new value, or press ENTER for the default
	Full Name []:
	Room Number []:
	Work Phone []:
	Home Phone []:
	Other []:
Is the information correct? [Y/n]
```

<br>

### 유저 삭제하기

만약 유저를 삭제하고 싶다면 아래와 같이 간단하게 입력하면 유저가 삭제됩니다.

```bash
deluser [username]
```

<br>

### 그룹에 유저 추가하기

이제 유저를 만들었으면 자신이 원하는 그룹에 넣으면 되는 데 다음과 같이 입력하면 됩니다.

```bash
usermod -aG [groupname] [username]
```

현재 유저가 속한 그룹을 알고 싶다면

```bash
groups
```

통하여 자신이 속한 그룹리스트를 볼 수 있습니다.<br>

그룹 구성원 확인

```bash
cat /etc/group | grep [groupname]
```

## sudo 설정

[sudo manual](https://www.sudo.ws/docs/man/1.8.14/sudoers.man/)<br>
