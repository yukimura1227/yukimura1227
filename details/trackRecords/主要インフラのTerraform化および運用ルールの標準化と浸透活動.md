# 主要インフラのTerraform化および運用ルールの標準化と浸透活動

インフラ環境をTerraform化し、運用ルールを整備し浸透活動を実施

インフラ環境に対する変更について以下のような課題がありました。

- インフラ変更に関するレビューが難しい
- インフラ変更に関するTry and Errorがやりづらい
- インフラのノウハウの蓄積・横展開が難しい

上記課題を解決するため、
以下のStepで改善・浸透活動を続け、最終的に主要なインフラのTerraform化を実施し、開発メンバー全員がTerraformスクリプトを調整する状態まで浸透させきりました。

1. 別の課題で、主要インフラを刷新することにしたので、その際にTerraform化を実施
1. Terraformに関してレビュー/反映フローの叩きを提案・推進
1. Terraformのハンズオンを実施
1. 運用を実施(適宜サポート)

以下、運用フローの叩き

```mermaid
graph TD

0(検証環境で検証しながらtfを構築/検証) --> 0.1
0.1(ステージング/本番環境用tfを構築し検証環境用tfと差分がないことを確認) --> 1
1(PRの作成<br/>ステージング環境/本番環境へのplanをPRに明記) --> 2
2(ステージング環境反映前に開発メンバーに反映する旨とPRを共有) --> 3
3(ステージング環境に向けてterraform apply) --> 4
4{問題なし?} -- No --> 0
4 -- Yes --> 5
5(本番環境反映前に開発メンバーに反映する旨を共有) --> 6
6(本番環境に向けてterraform apply) --> 7
7(問題なければPRをマージして完了)

style 0 fill:#080 ,color:white
style 0.1 fill:#080 ,color:white
style 1 fill:#080 ,color:white
style 2 fill:#f60 ,color:white
style 3 fill:#f60 ,color:white
style 4 fill:#f60 ,color:white
style 5 fill:#00a ,color:white
style 6 fill:#00a ,color:white
style 7 fill:#00a ,color:white
```
