---
tags: memo,computer,gpg
---

# 公開鍵の諸々

## SSH

- ```ssh-keygen -t ed25519 -C "comment"```

## GnuPGの使い方

### master keyの作成・設定

- ```gpg --full-generate-key --expert```
    - 鍵の生成
- ```gpg --output KEYID.gpg-revocation-certificate --gen-revoke```
    - 失効証明書の作成(もしものため)
- ```gpg --edit-key KEYID```


### 例

- 暗号化
    - ```gpg --symmetric hoge.txt```
    - ```gpg -c hoge.txt```
        - パスフレーズで暗号化
    - ```gpg --encrypt --recipient alice@example.com hoge.txt```
        - 受信者を指定して暗号化
- 復号化
    - ```gpg --decrypt hoge.txt.gpg```
    - ```gpg -d hoge.txt.gpg```
- 署名
    - ```gpg --clearsign hoge.txt```
- 鍵の管理
    - ```gpg --import public.gpg```

### 一覧
| コマンド       | 短縮名    | 概要                 |
| -------------- | --------- | -------------------- |
| --generate-key | --gen-key | 対話モードで鍵の生成 |

## 参考
- https://wiki.archlinux.jp/index.php/GnuPG
- https://text.baldanders.info/openpgp/gnupg-cheat-sheet/
- https://gist.github.com/hatsusato/1d5f0267bc9d02bb24c60bd7acc5a59a#note4
- http://joemphilips.com/post/gpg_memo/