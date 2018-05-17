# POV-Ray
いいかんじにレイトレーシングできる．
数値計算の結果とかをいいかんじにしようと思えばかなりいいかんじにできる(NAOJも使ってたはず

## Build
```sh
git clone https://github.com/POV-Ray/povray
cd povray
git checkout origin/latest-stable
cd unix
./prebuild.sh
cd ..
./configure COMPILED_BY="sksat <sksat.tec@gmail.com>"
make
sudo make install HOME=/home/sksat/
```

最後のmake installのとこだけ公式のREADMEと違うけど，こうしないとroot/.povrayに設定ファイルが入ってしまう．

## Benchmark
```
povray --benchmark
```
