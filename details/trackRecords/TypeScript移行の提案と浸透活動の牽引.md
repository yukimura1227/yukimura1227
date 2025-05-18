# TypeScript移行の提案と浸透活動の牽引

脱CoffeeScriptのモチベーション向上も見越してTypeScript導入と浸透活動(活動中)

10年もののRailsアプリケーションにおいて、肥大化し、現代には合わなくなってしまっているCoffeeScriptを削っていくため、TypeScript環境を整備して、新しいものはTypeScriptを利用するように牽引しました。脱CoffeeScriptにあたって、VanillaJSという筋も考えましたが、jsのテストコードを書く文化が構築できていないため、テストがなくてもある程度安全でかつ段階的に安全度をあげていけるようTypeScriptを採用しました。新しい技術の方が、開発メンバーのモチベーションも上げやすいという狙いも含みます。

以下のような流れで実現しています。

1. webpackerの導入(※ 最終的に脱webpackerをしています)
1. TypeScriptが利用できるようwebpacker(webpack)の整備
1. Sample実装の実施
1. 各チームにいくつかTypeScript移植を実施してもらう
    - 不明点や課題点の吸い上げと解決サポートを実施(実際にはほとんど必要なかった)
    - TypeScriptに対する不安感を払拭し、TypeScript移行の納得感を養生
1. 新しいScriptは、TypeScriptにしていく方針を明文化
1. 古いものも,開発チーム全体で徐々に移行(途中)
