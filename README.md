# AWSEmailToLineBot

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## 概要

AWSEmailToLineBotは、AWS LambdaとSESを使用して、メールを受信し、LINEに通知するためのサーバーレスアプリケーションです。

## 動作環境

- Node.js 12.x
- AWS CLI

## インストール

1. このリポジトリをクローンします。

    ```bash
    git clone https://github.com/{your_username}/AWSEmailToLineBot.git
    ```

2. 必要なnpmパッケージをインストールします。

    ```bash
    npm install
    ```

3. AWS CLIを使用して、AWS Lambda関数をデプロイします。

    ```bash
    aws lambda create-function --function-name {function_name} --zip-file fileb://function.zip --handler index.handler --runtime nodejs12.x --role {role_arn}
    ```

4. AWS SESで受信ルールを設定し、Lambda関数をトリガーとして指定します。

## 使い方

1. LINE Notify APIのアクセストークンを取得します。

2. `.env.sample`ファイルを`.env`にリネームし、アクセストークンを設定します。

    ```
    LINE_NOTIFY_ACCESS_TOKEN=your_access_token
    ```

3. AWS SESでメールを送信します。メールは、`to`フィールドに指定されたアドレスに送信されます。

4. LINEに通知が送信されます。

## ライセンス

このプロジェクトは、MITライセンスの下で公開されています。詳細については、[LICENSE](LICENSE)を参照してください。
