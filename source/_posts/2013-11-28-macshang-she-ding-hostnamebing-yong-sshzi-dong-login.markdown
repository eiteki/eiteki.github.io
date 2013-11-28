---
layout: post
title: "MAC上設定hostname並用SSH自動login"
date: 2013-11-28 19:19
comments: true
categories: 
---

#### 設定hostname
* 在~/.ssh之下打開config檔案（若沒有就手動建立一個），內容可以寫成
Host mySite
	HostName dev.eiteki.com
	User root
* `Host mySite`這行設定讓我們在ssh的時候可以輸入`ssh mySite`而不用輸入`ssh root@dev.eiteki.com`
* User的值就是登入進去的使用者名稱
* 若要設定多個hostname，每個設定用一行隔開，例如：
	Host mySite
	HostName dev.eiteki.com
	User root
	
	Host testSite
	HostName dev.test.com
	User anotherUser
	
#### Password-less SSH login
* 若~/.ssh之下沒有key，用`ssh-keygne`產生一組key，default會存在~/.ssh/id_rsa
* 接下來我們需要複製key到我們想要設定的remote server，可以用下面的指令
	`cat ~/.ssh/id_rsa.pub | ssh user@remotehost 'cat >> ~/.ssh/authorized_keys'`

設定完成之後，就可以用`ssh hostname`自動登入遠端機器了。

Reference: [How to set up an SSH config file in Mac OS X](http://ivetetecedor.com/how-to-set-up-an-ssh-config-file-in-mac-os-x/)
[How to Set Up a Password-less SSH Login](http://osxdaily.com/2012/05/25/how-to-set-up-a-password-less-ssh-login/)
