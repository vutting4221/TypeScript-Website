---
display: "Watch Options"
---

TypeScript 3.8 にてディレクトリを監視するための新戦略をリリースしました。これは、`node_modules` の変更を効率的に検知するために極めて重要なものです。

Linux のような OS において、TypeScript は 依存関係の変更を検出するために、`node_modules` と多くのサブディレクトリに、(ファイルウォッチャーではなく)ディレクトリウォッチャーをインストールします。
なぜなら、利用できるファイルウォッチャーの数を、`node_modules` のファイル数がしばしば上回る一方で、追跡するディレクトリ数は少なく済むからです。

各プロジェクトは異なる戦略の下でより良く動作する可能性もあり、逆にこの新しいアプローチが一連の作業の流れでうまく動作しない可能性もあります。そのため、TypeScript 3.8 では新しく `watchOptions` フィールドが導入されました。このフィールドでは、ファイルやディレクトリを追跡する為に、どの監視戦略を使用すべきか、compiler/language serviceに伝えることができます。
