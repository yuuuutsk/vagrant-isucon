# vagrant-isucon/isucon7-qualifier

## Overview

isucon7予選とほぼ同じ環境を構築するためのVagrantfileです。

ssh agent forwardしています
githubからは基本 git://

## Usage

- vagrant実行環境を用意する
- このリポジトリ内のVagrantfileを手元に用意する
  - 必要に応じてVagrantfileを編集する
- Vagrantfileがあるディレクトリで`vagrant up`を実行する
  - ベンチマーク用サーバ(bench)と参加者用サーバ(image)が起動
- Ansibleによるプロビジョニングが完了したら`vagrant ssh`を実行する
  - vagrant ssh bench
  - vagrant ssh image
- ベンチマークを実行する
  - sudo -i -u isucon
  - cd isubata/bench
  - bin/bench -remotes (imageサーバのIPアドレス)

## 動作確認


## 本来の設定と異なるところ


## FAQ

### ブラウザで動作確認ができない

Vagrantfileのネットワーク設定がデフォルトのままなので、サーバに割り当てられたIPアドレスにブラウザでアクセスしてみてください。
よくわからない場合は`# config.vm.network "private_network", ip: "192.168.33.10"`のコメントを外してブラウザから192.168.33.10にアクセスしてみてください。

### Vagrantがない環境で試したい

Ubuntu環境を用意できるのであれば[matsuu/ansible-isucon](https://github.com/matsuu/ansible-isucon)をご利用ください。
