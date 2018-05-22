# OpenRocket

[GitHub](https://github.com/openrocket/openrocket)

## Build
jdk7とant(javaのmakeみたいなやつ)が必要．
```
$ yaourt -S jdk7-openjdk
$ yaourt -S apache-ant
```

あとはmakeみたいにできる．
```
$ ant clean
$ ant build
$ ant check
$ ant unittest
```

ビルドに成功すると，
```
java -jar swing/build/jar/OpenRocket.jar
```
で実行できる．

# Source
coreとswingに分かれてるけど，シミュレーションとかのコードがあるのはcoreの方．
swingというのはGUIのライブラリらしい．
coreの方に出来たjarは実行出来なかったから，多分シミュレーションとかの実装をライブラリっぽいかんじにしてそれをswingから使ってる，みたいなかんじ．

大体見たいコードはcore/src/net/sf/openrocket下にある．
なんでこんなにディレクトリもファイルも多いんだ．．．

|パス|メモ|
|:---|:---|
|file/openrocket/OpenRocketSaver.java|orkファイル(zipの中の方)|
|simulation/RK4SimulationStepper.java|シミュレーションの本体|
