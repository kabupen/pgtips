# Docker

## command
新しいコマンド構造 `docker container + <command>` は versino 1.13 から追加されたコマンド群であり、今後はこの形式が推奨される。

|docker +||||
|:--:|:--:|:--:|:--:|
|container | attach || 実行中のコンテナにアタッチ(接続)する  |
|          | ls ||実行状態のコンテナの一覧を取得|
|          |    | -a |停止中のコンテナも表示 | 
|          | list || |
|          | run || イメージからコンテナを作成する|
|          |  | -it | 標準入力を渡し、ターミナルを立ち上げる|
|          |  | -d | デタッチしてバックグラウンドプロセスとする|
|image          | ls || インストールされているイメージの一覧を取得|
|       ||



## ビルド

## 実行する

### コンテナの環境でコマンドを実行する

```shell
docker container run tensorflow/tensorflow:1.15.5-gpu-py3 python --version 
```

### コンテナの環境でターミナルを起動する

```shell
docker container run -it tensorflow/tensorflow:1.15.5-gpu-py3
```

### バックグラウンドで実行する

- `-it` と `-d` オプションでターミナルを起動したままバックグラウンドプロセスとする
- 実行状態のコンテナは `ls` で確認できる
- 実行状態のコンテナに接続するには `attach` を使用することができる

```shell
user$ docker container run -it -d tensorflow/tensorflow:1.15.5-gpu-py3

user$ docker container ls
CONTAINER ID   IMAGE                                  COMMAND       CREATED         STATUS         PORTS     NAMES
93b5357a6497   tensorflow/tensorflow:1.15.5-gpu-py3   "/bin/bash"   4 seconds ago   Up 3 seconds             dreamy_kirch

user$ docker container attach 93b5357a6497
root@93b5357a6497:/# 
```
