# AsciiDoc
MarkDownよりいいかんじの機能がある．
includeとか良さ．
だがツールがちょこちょこ古く．．．

## Install
asciidocもあるけどasciidoctor(Ruby製)の方が良さそう．
asciidoctorはgemだからgem installで入る．
でも，拡張用のgemとかも使うことを考えるとGemfileでガッとやった方が良さそう．

```Gemfile
source "https://rubygems.org"
gem "asciidoctor"
```

## 文法
[ここ](https://takumon.github.io/asciidoc-syntax-quick-reference-japanese-translation/)を見ろ．

## 拡張

### PDF出力
```Gemfile
gem "asciidoctor-pdf"
gem "asciidoctor-pdf-cjk"
```

gemを入れたら
```
asciidoctor-pdf hoge.adoc
```
とかやれば:ok:

### コードハイライト
ハイライターがいくつかあるので，ハイライターを指定する．
```hoge.adoc
:source-highlighter: coderay
```

ハイライターは以下のようなものがある．
- coderay
- highlightjs
- prettify
- pygments

PDF/HTML両方に出力する可能性があって，
asciidoctorを使っているならcoderayが無難っぽい．

```Gemfile
gem "coderay"
```

### 数式

#### asciidoctor-latex
```Gemfile
gem "asciidoctor-latex"
```
texとhtmlに出力できる．
```
asciidoctor-latex -b html hoge.adoc
```
でHTMLが出力される．
これは特に変なことはしてなくて，数式部分にMathJaxを適用するようにしてるだけ．  

```
asciidoctor-latex hoge.adoc
```
でtexファイルが出力される．
だけどREADMEに書いてある通りに
```
xelatex hoge.tex
```
とかやってもコンパイル通らなかった．．．何故．．．

#### asciidoctor-mathematical
```Gemfile
gem "asciidoctor-mathematical"
```
asciidoctor-pdfとかと合わせて使う．
mathematicalを使用して事前に数式表現をpng/svgにしていいかんじに参照してくれる．．．はずなのだが．．．

書き方は適当に[サンプル](https://raw.githubusercontent.com/asciidoctor/asciidoctor-mathematical/master/sample.adoc)を見る．

コマンドは
```
asciidoctor-pdf -r asciidoctor-mathematical hoge.adoc
```

でいけるはず．
はずだが，\sqrt{}が爆発した．
![自我を失ったsqrtの姿](https://pbs.twimg.com/media/DdJuUP-UQAAyMXe.jpg:large)
一応開発は止まっていないみたいなので，そのうち直ってたりIssue送ったら直るとかはあるかもしれなくはある．
mathematical自体の問題でなければ，
どうにかなりそうな気はする(asciidoctor-mathematicalはそこまで多くの処理をしていなさそう)．
でも，mathematicalはTeXの数式をいい感じに画像にコンパイルしてくれているはずなので．．．？

自分でツールを書くという手もなくは無いが，Rubyよくわからんしなあ．．．
