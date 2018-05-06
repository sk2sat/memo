# SATySFi
## インストール

基本的にREADMEの通りでOKだけどopamが古くてかつシェルがfishだと死ぬのでopam2を入れること．
```
yaourt -S opam2
opam init
```

ビルドは以下
```
git clone https://github.com/gfngfn/SATySFi.git
cd SATySFi
opam pin add satysfi .
opam install satysfi
```
