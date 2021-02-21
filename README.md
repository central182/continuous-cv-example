# An example of continuous compilation of `.md` CVs

Recently I've created a private repository for tracking my current job-hunting status:
a potential opportunity will have its own *Issue*, where feedback will be updated as comments.

The CVs (possibly in different languages) fit naturally as the *Code* of the repository, and consequently it was necessary to automate the compilation of `.md` files to, well, some non-techie format.

You can find the artifacts built from this `README.md` at the latest run of [https://github.com/central182/continuous-cv-example/actions/workflows/compile.yaml](https://github.com/central182/continuous-cv-example/actions/workflows/compile.yaml).

## `.md` to `.pdf`
There's a catch in using the `pdflatex` engine of `pandoc` to create `.pdf` files: there can't be any Unicode characters in the source `.md` files.

The `wkhtmltopdf` engine, on the other hand, works perfectly with Japanese characters, and is therefore being used in my current workflow. I've tweaked a bit the default CSS styles as well.

## `.md` to `.docx`
`.docx` files are for agents who want to stamp their logo on my CVs. It's a pity that `pandoc` doesn't provide an option to change the paper size of the output `.docx` file.

# `.md`形式の履歴書などを継続的に自動コンパイルする例

近頃転職活動を始めたので、プライベートリポジトリを作ってそこで進捗管理などをしています。
応募しようとしているポジションごとにIssueを作って、フィードバックなどをコメントに順次更新していくという構想です。

履歴書などはリポジトリのCodeとして格納し、`.md`ファイルを非技術者向けのフォーマットに自動的にコンパイルする仕組みを用意しました。

この`README.md`からビルドされた成果物は、[https://github.com/central182/continuous-cv-example/actions/workflows/compile.yaml](https://github.com/central182/continuous-cv-example/actions/workflows/compile.yaml)の一番直近の実行結果にてご確認いただけます。

## `.md`から`.pdf`への変換
`pandoc`の`pdflatex`エンジンを使って`.pdf`ファイルを生成させる場合、もととなる`.md`ファイルに日本語の文字が入っていると失敗してしまうので、それを回避すべく`wkhtmltopdf`エンジンを採用しました。CSSの微調整も施してあります。

## `.md`から`.docx`への変換
転職エージェントのなかには、自社のロゴをあとから追記したいという方もいらっしゃるので、そういう方には`.docx`ファイルの方を送付します。`pandoc`で出力ファイルの用紙サイズを指定できないのが少し残念に思えました。
