---
layout: post
title: "SSH into virtualbox VM"
date: 2013-08-18 17:51
comments: true
categories: linux
---

我在virtualbox開了一台ubuntu server版的VM，拿來練習web相關技術。但想要把裡面的網頁透過host端的瀏覽器顯示出來，所以想到要用ssh連進去VM，以下是我嘗試還有正在學習的方法

#### NAT, port forwarding
* 參考[Howto use SSH local and remote port forwarding](http://www.debianadmin.com/howto-use-ssh-local-and-remote-port-forwarding.html)中的Remote port forwarding，但第一步就不知道怎麼做了

#### 從virtualbox中進行bridge設定
環境：mac OSX 10.8.4, virtualbox 4.2.16
參考[SSH into your Virtualbox VM from the same computer](http://www.youtube.com/watch?v=5BsShkcweIs)

1. 打開virtualbox，選擇想要連進去的VM，按下`設定值`
2. 選擇`網路`，在`介面卡1`裡面的`附加到`欄位，改成`橋接介面卡（Bridge Adapter）`
3. 啟動VM，在terminal輸入`ifconfig`查詢網路資訊，在eth0的inet addr就是ssh的位址（	eg. 192.168.2.104）
<br>這樣就ok了，但如果host的網路ip有變，就要在確認一次VM的ip，否則原來的ip是不對的。

在host端的操作就是：
{% codeblock %}
ssh 192.168.2.104
{% endcodeblock %}
</br>然後就能快樂的使用它囉!

