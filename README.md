# Stacked PR Demo

GitHub Stacked PR を試すための最小リポジトリです。

## まず必要なもの

1. GitHub CLI `gh`
2. Stacked PR 用の拡張機能

```bash
gh extension install github/gh-stack
```

3. GitHub へのログイン

```bash
gh auth login
```

## このリポジトリの構成

- `main`: ベースブランチ
- `feature/01-setup`: 1 つ目の PR
- `feature/02-add-logic`: 2 つ目の PR
- `feature/03-add-docs`: 3 つ目の PR

## 3 ブランチでの流れ

このリポジトリにはすでに 3 本のブランチがあるので、既存ブランチをそのままスタックとして取り込みます。

```bash
gh stack init --base main feature/01-setup feature/02-add-logic feature/03-add-docs
```

その後は、上から順に確認できます。

```bash
gh stack view
gh stack checkout feature/01-setup
gh stack checkout feature/02-add-logic
gh stack checkout feature/03-add-docs
```

PR を GitHub に作成するところまで進めるなら、最後に submit します。

```bash
gh stack submit
```

## ブランチの役割

- `feature/01-setup`: 初期ファイルを追加する
- `feature/02-add-logic`: サンプルロジックを追加する
- `feature/03-add-docs`: 手順説明を追加する

## 運用メモ

- 1 つの PR には 1 つの論理変更だけを載せる
- 下流のブランチは上流ブランチの差分を前提にする
- 途中の PR がマージされたら、後続ブランチを `gh stack sync` で追従させる

## スタックへのブランチ追加

- git コマンドではなく gh stack add <branch> で追加する
