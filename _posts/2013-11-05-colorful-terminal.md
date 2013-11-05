---
title: 把Terminal 變彩色
layout: post
comments: true
tags: [ps1, terminal, mac-os]
---

Mavericks 的Terminal 預設的顏色有些單調。我們可以用[PS1 產生器][1]加點顏色。有顏色的PS1 方便在輸出訊息中找到指令的位置。下面是我的設定：

{% highlight bash %}
export PS1="\[\e[00;33m\]\t\[\e[0m\]\[\e[00;37m\] \[\e[0m\]\[\e[00;32m\]\u@\[\e[0m\]\[\e[00;36m\]\h:\[\e[0m\]\[\e[00;35m\]\W\[\e[0m\]\[\e[00;31m\]\$\[\e[0m\]\[\e[00;37m\] \[\e[0m\]"
{% endhighlight %}

另外也可以將`ls` 指令加上`-G` 參數，用不同的顏色標記不同類型的檔案：

{% highlight bash %}
alias ls='ls -G'

{% endhighlight %}

把上面的指令貼到`~/.profile` ，再開新分頁就可以看到效果。

[1]: http://bashrcgenerator.com 

