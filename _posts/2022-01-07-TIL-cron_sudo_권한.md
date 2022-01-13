---
title: "cron sudo 권한"
date: 2022-01-07 23:32:12 +0900
categories: TIL
tags: cron crontab
---

## cron이란?

cron은 유닉스 계열 컴퓨터 운영 체제의 시간 기반 잡 스케줄러이다.<br>
즉 원하는 시간에 원하는 작업을 설정하면 자동으로 실행해주는 편리한 프로그램입니다.<br>
cron은 기본적으로 crontab (cron table)라는 파일에 입력된 잡 목록을 실행시킵니다<br>
그렇다면 정확히 crontab은 무엇일까요?

## crontab 이란?

crontab은 cron이 실행시켜야할 잡 목록들을 가지고 있습니다.<br>
crontab을 편집하여 원하는 시간에 원하는 작업이 실행되도록 할 수 있습니다.

```bash
crontab -e
```

위와 같은 명령어를 통해 crontab을 편집할 수 있습니다. 다만 crontab은 각각의 유저 및 root 모두 달리 설정할 수 점에 유의 해서 작성하여야 합니다.<br>

[빠르게 crontab 작성하기](https://crontab.guru)

crontable의 형식은 다섯자리로 이루어져 있으며 각각의 자리는 시간단위를 의미합니다.

```bash
minute hour day(month) month day(week) command
```

ex)

```bash
*/10 * * * * command
```

예시를 보시게 되면 매 10마다 command를 실행한다는 뜻이 됩니다.<br> \* = 모든 값<br>
/ = 단계 값 (해당 위치의 단위 값)<br>
@reboot = 부팅시에 실행<br>
이것 말고도 다양한 표현이 존재하며 참고하셔서 crontab을 편집하시면 될것 같습니다.
