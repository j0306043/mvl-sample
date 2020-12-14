# 多値論理研究会用*非*公式LaTeXスタイルファイル

多値論理フォーラム(以下、フォーラム)や多値論理とその応用研究会(以下、二種研)の論文執筆のためのLaTeXスタイルファイルです。
平山が個人的に勝手に作った非公式なものですので、本スタイルファイルの使用により生じた結果に、平山は一切責任を負いません。

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
\renewcommand{\mvlvolume}{39} % 多値論理フォーラムの巻号
\renewcommand{\mvlpresennumber}{1} % 多値論理フォーラムの発表番号
\renewcommand{\mvlyear}{2016} % 年
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
- documentclassには比較的原始的な`jarticle`(sなし)を使用することを想定しています。日本語用に洗練された`jsarticle`(sあり)だと、文字サイズが10pt以外のときに見た目がおかしくなります。`jarticle`を想定している理由は、英語と日本語の両方に対応させるためや、余白の調整がしやすいためです。
