---
title: "Git Branch"
date: 2021-07-12 15:17:20 +0900
categories: TIL
---

<h2>Git Branch</h2>
원본 버전은 유지한 상태에서 다른 기능을 추가하고 싶을 때 branch를 사용한다.
branch는 뜻 그대로 가지를 생각하면 이해하기가 싶다. 동료와 협업이나 다른 기능을 넣을 때 branch를 이용해 분기한다.

<h3>사용법</h3>

{% highlight ruby %}
git branch # 뒤에 원하는 branch이름을 작성하면 branch가 현재 HEAD에 생성됨
git checkout # 원하는 branch로 이동
{% endhighlight %}

<h3>merge</h3>

{% highlight ruby %}
git merge # 합칠 branch(ex.master)에서 합쳐질 branch를 입력함
{% endhighlight %}

분기된 branch는 merge를 통해 다시 합쳐질 수 있다.
합쳐질때는 3way merge라는 방법을 사용하는 데

<img src="https://media.giphy.com/media/cFkiFMDg3iFoI/giphy.gif" alt="git merge.gif">

두개의 커밋의 공통 조상을 사용하여 merge를 실행한다.

공통된 조상과 비교하며 한쪽에서만 바뀐 경우는 바로 반영하고
공통된 내용을 두 커밋이 둘다 수정하였으면 충돌을 발생 시킨다.
