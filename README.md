東京大学の電気系学科の卒業/修士/博士論文の表紙っぽい表紙を作成するパッケージです。非公式非公認です。

## Requirements
フォントの都合上`luatexja-fontspec`を使用しているのでLuaTeXでないと動きません。


## 使い方
`eeictitlepage.sty`をメインの`.tex`ファイルと同じディレクトリに置き、`\usepackage{eeictitlepage}`で読み込みます。

`\author`など(例を参照)で内容を指定し、`document`内に`\eeictitlepage`と書くと表紙が生成されます。

### フォントについて
あの表紙を忠実に再現しようとすると`HG正楷書体-PRO`(`HGRSKP.TTF`)というフォントが必要です。残念ながらMacやOverleafのデフォルトのフォントではありません。購入すると2万円ほどします。

幸い、このフォントはWindowsにOffice365をインストールすると`C:\Windows\Fonts`にダウンロードされます。私は学科PCにOfficeを入れてからフォントファイルをMacに移植しました。

#### フォントをインストールした場合
`\titlepagefont{HGSeikaishotaiPRO}`と書いてフォントを指定してください(例を参照)。

#### フォントファイルを直接使う場合(Overleaf等)
フォントファイルを`.tex`ファイルと同じディレクトリに配置し、`\titlepagefont{[フォント名.TTF]}`でフォントを指定してください(例を参照)。

#### フォントなんて気にしない場合(正解)
`\titlepagefont`を指定しない場合はデフォルトのフォントが適用されます。



## 例
##### コード
```tex
\documentclass{ltjsarticle}
\usepackage{luatexja}

\usepackage{eeictitlepage}

% define ----------
\titlepagefont{[HGRSKP.TTF]} % フォントファイルを配置した場合
% \titlepagefont{HGSeishotaiPRO} % フォントをインストールした場合

\bigtitle{卒業論文}

\title{卒論をさいごの日まで残して\\おいた時の家族と自分の反応}
\date{\formatdate{8}{2}{2023}} % アメリカ式(d-M-yyyy)

\professor{東大　太郎}{教　授}
\secondprofessor{本郷　一郎}{准教授} % optional
\thirdprofessor{駒場　二郎}{講　師} % optional

\department{電子情報工学科}
\studentnum{01-234567}
\author{電気　太郎}
% ------------------

\begin{document}

\eeictitlepage % タイトルの挿入

\end{document}
```

##### 出力
![](example.png)

## 参考文献
[https://nlab.itmedia.co.jp/nl/articles/1909/09/news080.html](https://nlab.itmedia.co.jp/nl/articles/1909/09/news080.html)