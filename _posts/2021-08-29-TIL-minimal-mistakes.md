---
title: "Minimal-mistakes"
date: 2021-08-28 21:53:20 +0900
categories: TIL
tags: Gitbub blog
---

# Minima-mistakes 시작하기

minimal mistakes를 사용해 github에 블로그를 호스팅하는 방법입니다.

## 사전에 알아야할 지식

- Ruby
- [Bundler](https://bundler.io)
- [Jekyll](https://jekyllrb.com)
- Markdown

### Bundler

Bundler는 ruby 프로젝트의 일정한 환경관리를 제공합니다. 필요한 gems과 버전을 설치 및 관리합니다.
간단하게 블로그를 호스팅하기 전에 필요한 설치파일를 관리한다고 생각하면 될 것 같습니다.

minimal mistakes는 Gemfile이 준비 되어 있어 bundle을 사용하여 실행시키면 됩니다.

```
bundle exec [OPTIONS]
```

### Jekyll

Jekyll는 정적인 사이트 생서기입니다. markup 언어로 쓰여진 텍스트와 layout들을 사용하여 정적인 웹사이트를 만들어줍니다.

```
jekyll new NAME
```

을 통해 바로 시작할 수 있습니다. minimal-mistake는 jekyll로 만들어 졌기 때문에 원하는 기능을 추가 하고 싶을 때는
jekyll의 공식 문서를 참고하면 됩니다.

### Markdown

마크다운은 일종의 마크업 언어의 종류이다. Jekyll은 마크다운파일을 인식해서 지정한 레이아웃에 맞게 렌더링해줍니다. 포스트할 때
이 마크다운을 잘 알고있어야 여러가지 링크나 사진을 같이 사용할 수 있습니다.
