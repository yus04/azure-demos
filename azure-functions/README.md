# azure-functions
Azure Functions デモ用のリポジトリです。

## 前提条件
- Azure CLI がインストールされていること
- [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools/blob/v4.x/README.md) がインストールされていること

## 操作手順
### ローカル開発環境のセットアップ
仮想環境を作成する
```bash
python -m venv .venv
```

仮想環境を有効化する
```bash
source .venv/bin/activate
```

(任意) 関数プロジェクトの作成
```bash
func init --python
```

(任意) 関数をプロジェクトに追加
```bash
func new --name HttpExample --template "HTTP trigger" --authlevel "anonymous"
```

必要なライブラリのインストール
```bash
pip install -r requirements.txt
```

関数のローカル実行
```bash
func start
```

### Azure へのデプロイ
ローカル関数プロジェクトをデプロイ (APP_NAME は作成済みの Azure Functions のリソース名)
```bash
func azure functionapp publish <APP_NAME>
```

## 参考ドキュメント
- Microsoft Learn「クイックスタート: コマンド ラインから Azure に Python 関数を作成する」
https://learn.microsoft.com/ja-jp/azure/azure-functions/create-first-function-cli-python?tabs=linux%2Cbash%2Cazure-cli%2Cbrowser
