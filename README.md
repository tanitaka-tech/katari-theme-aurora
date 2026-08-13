# Katari Aurora Themes

Katari エディタにオーロラをイメージした配色テーマを追加する拡張です。
テーマ専用拡張なので `main` を持たず、コードを 1 行も実行しません
（Worker も esbuild も起動しません）。中身は `manifest.toon` の静的宣言だけです。

## Themes

- Aurora Night — 深い夜空をベースに、紫・シアン・ピンクを合わせたダークテーマ
- Aurora Dawn — 淡い朝空をベースに、紫・青緑・ピンクを合わせたライトテーマ

選択すると `extension:tech.tanitaka.katari-theme-aurora:<テーマID>` として
名前空間化され、他の拡張のテーマとは衝突しません。
拡張を無効化・削除すると `Dark` に戻ります。

Katari の既存テーマ派生エンジンを使うため、4 つの seed から
エディタ全体のデザイントークンが生成され、
テキストと背景のコントラスト補正も自動で適用されます。

## Requirements

- Katari 0.2.0 以降（`min_app_version`）
- Extension API version 1

## Install

1. Katari で「拡張 → 拡張を管理...」を開く
2. 「URL から追加」に次の URL を貼り付ける
3. 内容を確認して拡張を承認する

    https://github.com/tanitaka-tech/katari-theme-aurora

承認後、「エディタ設定 → テーマ」と「表示 → テーマ」に
Aurora Night / Aurora Dawn が追加されます。

特定バージョンへ固定する場合:

    git+https://github.com/tanitaka-tech/katari-theme-aurora.git#v1.1.0

プロジェクトの `Extensions/manifest.toon` に依存として書くこともできます:

    dependencies:
      - id: tech.tanitaka.katari-theme-aurora
        ref: "git+https://github.com/tanitaka-tech/katari-theme-aurora.git#v1.1.0"

## Customize

配色は `manifest.toon` の 4 つの seed で定義しています。

- base   背景とパネル
- accent 主要な操作色
- sub    二次強調色
- pop    ごく一部の強調色

`overrides` では派生結果を個別に上書きできます。指定できるキーは次の通りです。

    bg_0 bg_1 bg_2 bg_3 border
    text_1 text_2 text_muted
    accent accent_2 accent_pop on_accent
    danger ok shadow

`shadow` 以外はすべて `#rrggbb` 形式です。
未指定のキーは派生エンジンが seed から生成します。

## License

MIT — 詳細は LICENSE を参照してください。
