# react-app
React のサンプルアプリケーションを動かすためのコードです。このリポジトリ内のコードは、以下のコマンドを実行して作成されたものです。

```
npx create-react-app app
```

## 実行手順
サンプルアプリケーションへのディレクトリへ移動

```
cd app
```

必要なライブラリのインストール
```
npm install
```

サンプルアプリケーションの起動
```
npm start
```

## 補足：.devcontainer について
ベースイメージや拡張機能など、コンテナ化された開発環境のカスタマイズが必要な場合は .devcontainer > devcontainer.json を編集した上で以下の対応をして下さい。
- GitHub Codespaces の場合
    - コマンドパレットから 「Codespaces: Full Rebuild Container」 を実行
- ローカル環境の場合
    - コマンドパレットから 「Dev Containers: Open Folder In Container」 を実行
    - (Dev Containers の拡張機能のインストールが必要)

## 参考文献
Create React App 「Getting Started」
https://create-react-app.dev/docs/getting-started/
