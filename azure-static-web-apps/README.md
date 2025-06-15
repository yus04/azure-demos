# azure-static-web-apps
Azure Static Web Apps デモ用のリポジトリです。

## 前提条件
- Azure Static Web Apps がデプロイ済み

## 操作手順
### サンプルアプリのローカル実行
以下を実行してローカルにて React アプリを実行。
詳細は react-app/README.md を参照。
```bash
cd react-app/app
npm install
npm start
```

### Azure へのデプロイ
必要なパッケージのインストール ([Azure Static Web Apps CLI (SWA CLI)](https://www.npmjs.com/package/@azure/static-web-apps-cli) がインストール済みの場合はスキップ可能)
```bash
npm install
```

swa-cli.config.json の作成/更新 (このまま一気通貫でデプロイまで実行可能)
```bash
npm run swa
```

(任意) アプリケーションのビルド
```bash
npm run swa:build
```

Preview 環境への SWA へのデプロイ (コマンド実行後に Choose your Static Web App と表示されたら、デプロイ先の SWA を選択する。)
```bash
npm run swa:deploy:preview
```

(任意) Production 環境への SWA へのデプロイ
```bash
npm run swa:deploy:production
```

## 付録
### 独自関数の持ち込みの設定
Azure ポータルにて、「静的 Web アプリ」>「API」>「運用」もしくは「環境のプレビュー」から Azure Functions をリンクした後、App.js を以下に書き換え、SWA をビルド・デプロイする

```js
import React, { useEffect, useState } from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  const [text, setText] = useState('');

  useEffect(() => {
    fetch('/api/HttpExample')
      .then((res) => res.text())
      .then((data) => {
        setText(data);
      })
      .catch((err) => {
        setText('Error: ' + err.message);
      });
  }, []);

  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          {text}
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

## 参考ドキュメント
- Microsoft Learn 「Azure Static Web Apps CLI を使用して静的 Web アプリをデプロイする」
https://learn.microsoft.com/ja-jp/azure/static-web-apps/static-web-apps-cli-deploy
- Microsoft Learn 「独自の関数を Azure Static Web Apps で使用する」
https://learn.microsoft.com/ja-jp/azure/static-web-apps/functions-bring-your-own
