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
