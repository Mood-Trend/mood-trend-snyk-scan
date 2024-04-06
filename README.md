# mood-trend-snyk-scan

`気分グラフ Mood Trend` の IaC 環境に対する差分検知リポジトリです。

## Overview

Snyk IaC によって `.tfstate` ファイル と 実際の Google Cloud プロジェクト環境を比較して、IaC 管理内／管理外のリソースチェックを `毎日 3:00` に実施します。

![snyk-iac-scan-architecture](https://github.com/Mood-Trend/mood-trend-snyk-scan/assets/39579511/30c8e3f5-1237-424a-b48a-268036986183)

- GitHub リポジトリ側
  - Cloud Build での Snyk IaC Scan の振る舞いを定義した yaml
  - Snyk IaC Scan 時に参照するバケット情報を定義した backend.tf
- Google Cloud 側
  - GitHub リポジトリを監視して、来たるタイミングで Snyk IaC Scan を実行する Cloud Build
  - 毎日 3:00 に Cloud Build を実行するように定義した Cloud Scheduler
  - .tfstate ファイルを保存するバケットを持つ Cloud Storage
  - Snyk IaC Scan の結果を出力する Cloud Logging

## Example Snyk Scan Results

![scan-result](https://github.com/Mood-Trend/mood-trend-snyk-scan/assets/39579511/813ec29c-4623-49ee-84e1-fc98cb68d900)  

## Click here for details

- [Snyk を使って Google Cloud の IaC 環境をセキュアに管理してみる](https://zenn.dev/nozomi_cobo/articles/snyk-iac-google-cloud)

## Other Repositories

- [mood-trend-flutter](https://github.com/Mood-Trend/mood-trend-flutter)
- [mood-trend-firebase](https://github.com/Mood-Trend/mood-trend-firebase)
- [mood-trend-terraform](https://github.com/Mood-Trend/mood-trend-terraform)
