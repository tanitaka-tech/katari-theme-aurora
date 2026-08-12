# Katari Aurora Themes

[Katari](https://github.com/tanitaka-tech/Katari) にオーロラをイメージしたテーマを追加する、宣言専用のエディタ拡張です。
Worker や実行コードを含まず、`manifest.toon` だけで動作します。

## Themes

- **Aurora Night** — 深い夜空をベースに、紫・シアン・ピンクを組み合わせたダークテーマ
- **Aurora Dawn** — 淡い朝空をベースに、紫・青緑・ピンクを組み合わせたライトテーマ

Katari の既存テーマ派生エンジンを利用するため、背景・テキスト・アクセントの各色は
エディタ全体のデザイントークンへ展開され、読みやすさのためのコントラスト補正も適用されます。

## Install

1. Katari で「拡張 → 拡張を管理...」を開く
2. 「URL から追加」に次の URL を貼り付ける
3. 内容を確認して拡張を承認する

```text
https://github.com/tanitaka-tech/katari-theme-aurora
```

承認後、「エディタ設定 → テーマ」と「表示 → テーマ」に Aurora Night / Aurora Dawn が追加されます。

特定バージョンへ固定する場合:

```text
git+https://github.com/tanitaka-tech/katari-theme-aurora.git#v1.0.0
```

## Requirements

- `contributes.themes` に対応した Katari
- Extension API version 1

## Customize

配色は [`manifest.toon`](manifest.toon) の4つの seed で定義しています。

- `base`: 背景とパネル
- `accent`: 主要な操作色
- `sub`: 二次強調色
- `pop`: ごく一部の強調色

`overrides` では派生後のテーマ変数を個別に調整できます。

## License

[MIT](LICENSE)
