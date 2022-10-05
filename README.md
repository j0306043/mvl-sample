# 多値論理研究会用*非*公式LaTeXスタイルファイル

多値論理フォーラム(以下、フォーラム)や多値論理とその応用研究会(以下、二種研)の論文執筆のためのLaTeXスタイルファイルです。
平山が個人的に勝手に作った非公式なものですので、至らぬところがございましたら、Issuesにご報告お願いします。

# ファイルの概要

- mymvlmacros.sty: スタイルファイル本体。
- sample.tex: サンプルのLaTeXソース。スタイルファイルの使用例。
- sample.pdf: sample.texのコンパイル結果。二種研の出来栄えの例。

# 使い方

フォーラムと二種研の両方に対応しています。
たいしたことはしていませんので、`sample.tex`を見れば、すぐ使えると思います。

- LaTeXソースと同じディレクトリに、`mymvlmacros.sty`ファイルを置きます。
- LaTeXソース中に、
  - フォーラムの場合は、下記を置きます。
  ```
  \usepackage[mvlforum]{mymvlmacros}
  ```
  - 二種研の場合は、下記を置きます。
  ```
  \usepackage[mvlnishuken]{mymvlmacros}
  ```
- フォーラムの場合は下記のパラメタを設定します。二種研の場合は不要です(設定しても無視されます)。
```
\renewcommand{\mvlvolume}{44} % 多値論理フォーラムの巻号
\renewcommand{\mvlpresennumber}{3} % 多値論理フォーラムの発表番号
\renewcommand{\mvlyear}{2021} % 年
\renewcommand{\mvlmonth}{9} % 月
```

# 補足説明

- 本スタイルファイルは、以下の4つを調整します。
  - 題目著者等のヘッダ部
  - ページの余白
  - ページ番号の有無
  - 参考文献の文字サイズ
- ページの上下左右の余白が、フォーラムと二種研のそれぞれの規定通りに自動的に設定されます。自分で余白を変更しないでください。
- フォーラムの場合は、自分の発表番号をつけたページ番号をページ下端につけることになっているので、それに対応しています。
- 二種研の場合は、ページ番号をつけないことになっているので、ページ番号を出さないようにしています。
- 参考文献の文字サイズをsmallにします。文献リストの行間スペースを削減します。
- 対応するTeXのバージョンとしては、TeX Live 2020以降をお使いください。
- `\documentclass`のクラスファイルには日本語用に注意深く作られたbxjsarticleを使用することを想定しています。
  - bxjsarticle使用の場合(推奨): 下記のように、`\documentclass`のオプションのLaTeXエンジン指定に`autodetect-engine`を指定しておけば、LaTeXエンジンが自動判定され、pLaTeX+dvipdfmx, LuaLaTeX, XeLaTeX, pdfLaTeXどれでも行けると思います(が、LuaLaTeXを推奨します)。補足ですが、`jbase=14.1Q`は和文フォントサイズを10ptにする指定です。おおよそ和文フォントの単位(Q:級)では、14.1Q=10ptです。
  ```
  \documentclass[autodetect-engine,dvi=dvipdfmx,ja=standard,twocolumn,jbase=14.1Q]{bxjsarticle}
  ```
  - jsarticle使用の場合(非推奨): pLaTeX+dvipdfmxの人でどうしてもjsarticleにしなければならない場合、下記のように`\documentclass`を宣言することで従来のjsarticleでも行けると思いますが、推奨しません。英語のみの論文であれば、article(jsなし)でも大丈夫です。
  ```
  \documentclass[twocolumn]{jsarticle}
  ```
