## 要点
- 以下の制約を考慮して、Automator のワークフローを作成した
    - 制約1：スクレイピングは、ある1つのサイトから情報を抜き出すには適しているhが、不特定多数のサイトから決まった情報を抜き出すのはとても面倒。  
    → ChatGPTのネット検索機能を使う。
    - 制約2： OpenAIのAPIではweb検索機能の提供はまだない  
    →ブラウザ版のChatGPTアプリ自体を自動化する
    - 制約3：ChatGPTに1度に複数の企業を訪ねると、探索するwebの範囲が狭くなったり、一部企業が抜け落ちたりする  s
    →1企業ずつ訪ねるのが良い
- Automatorとは、Mac標準搭載の自動化ツールである


## フロー
1. リファレンスの chatGPT_company_volume_research.zip をダウンロードして解凍する  
2. chatGPT_company_volume_research.csv に対象とする企業名を記載する（1行1企業名）  
    1. ※ファイルの中身は削除されるので、保管しておきたい場合はコピーを取っておく。  
3. Google Chromeで、ChatGPTにログインする  
4. Automator（Mac標準搭載）を開いて、chatGPT_company_volume_research.workflow を開く  
5. 一番下の「ループ」箇所に「100回後に自動的に停止する」とあるが、これを企業数に変更する。  
6. 右上の「実行」ボタンを押す  


## 編集したい時

- プロンプトを変えたい場合：
AutomatorのAppleScript内の「の売り上げ規模と、従業員数を教えて。」の箇所を編集する
    - 出力形式を数字にしたい等の要望も、プロンプトを変えて行うべし。
- ブラウザーを変えたい場合：
AutomatorのAppleScript内の「Google Chrome」を希望のブラウザーのアプリケーション名に変更する
- csvファイルの扱いを変えたい場合：
AutomatorのAppleScript前後の シェルスクリプト を変える必要がある
- その他（待機時間等）：
AppleScriptのどこを変えれば良いかは、chatGPTなどに「このコードを1行ずつ説明して」というと教えてくれる