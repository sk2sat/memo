# D言語

## インストール
コンパイラが複数ある
- dmd
- gdc(gcc backend)
- ldc(LLVM backend)

dmdをLinuxに入れるには，パッケージマネージャor``curl -fsS https://dlang.org/install.sh | bash -s dmd``

## パッケージマネージャ
- dub

```
$ dub init hello
$ dub build
$ dub run
```
ビルドタイプは-bで指定．
```
$ dub build -b release
```

