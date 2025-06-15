# azure-static-web-apps
Azure Static Web Apps デモ用のリポジトリです。

## 前提条件
- Azure Static Web Apps がデプロイ済み

## 操作手順
### サンプルアプリのローカル実行
以下を実行してローカルにて React アプリを実行。
詳細は react-app/README.md を参照。
```
cd react-app/app
npm install
npm start
```

### Azure へのデプロイ
必要なパッケージのインストール ([Azure Static Web Apps CLI (SWA CLI)](https://www.npmjs.com/package/@azure/static-web-apps-cli) がインストール済みの場合はスキップ可能)
```
npm install
```

swa-cli.config.json の作成/更新 (このまま一気通貫でデプロイまで実行可能)
```
npm run swa
```

SWA へのデプロイ (コマンド実行後に Choose your Static Web App と表示されたら、デプロイ先の SWA を選択する。)
```
npm run swa deploy
```

## 参考ドキュメント
- Microsoft Learn 「Azure Static Web Apps CLI を使用して静的 Web アプリをデプロイする」
https://learn.microsoft.com/ja-jp/azure/static-web-apps/static-web-apps-cli-deploy
