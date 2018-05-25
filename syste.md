# systemd

https://wiki.archlinux.jp/index.php/Systemd
https://www.slideshare.net/moriwaka/systemd
http://enakai00.hatenablog.com/entry/20130917/1379374797

## Unit

パス
- /lib/systemd/{system, user}
	パッケージで配置される
- /etc/systemd/{system, user}
	自分で編集・設定される．優先される．
- /run/systemd/{system, user, generator}
	動的に生成される
