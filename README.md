# lima

limaのDebian + Dockerなど開発環境の立ち上げ

Docker と go と rustが動作する環境を作っている
Silicon用で作成

| 名称   | 用途 |
|------|----|
| go   |    | 
| rust |    | 

| 名称         | 用途 |
|------------|----|
| Starship   |    | 
| eza        |    | 
| bat        |    | 
| procs      |    | 
| hexyl      |    | 
| tokei      |    | 
| bottom     |    | 
| du-dust    |    | 
| lazydocker |    | 
| lazygit    |    | 

https://github.com/lima-vm/lima

```shell
limactl start --name=default debian12-arm.yaml
```

```shell
limactl stop 
limactl delete
```

```shell
limactl stop default 
limactl delete default 
limactl start --debug --name=default debian12-arm.yaml 
```

```shell
limactl stop  
limactl start 
```

```shell
limactl shell default
```
```shell
ssh -F ~/.lima/default/ssh.config lima-default
````

# lima コマンド

## 開始

```shell
limactl start 
```

## Linuxインスタンスを一覧

```shell
limactl list
```

# 削除

```shell
limactl delete 
```

```shell
limactl stop 
```

```shell
limactl shell 
```

# Java
java -version

# Docker (ユーザー権限)
docker info

# Python
python3 --version

# Rust
rustc --version

# Go
go version

# Node.js
node -v

```shell
# すべてのコンテナを停止
docker stop $(docker ps -a -q)

# システム全体のクリーンアップ
docker system prune -f

# 停止されたコンテナの削除
docker container prune -f

# 全てのコンテナを強制削除
docker rm -f $(docker ps -a -q)

# 使用されていないイメージの削除
docker image prune -f

# すべてのイメージを削除
docker rmi -f $(docker images -a -q)

# 未使用のボリュームを削除
docker volume prune -f

# 未使用のネットワークを削除
docker network prune -f


```

https://dev.classmethod.jp/articles/lima-using-vm-on-macos-without-parallels-vmware/
https://github.com/lima-vm/lima/discussions/1890
ssh -F ./ssh-config lima-default

cat  ~/.lima/default/ssh.config

ssh -F ~/.lima/default/ssh.config lima-default

https://github.com/lima-vm/lima/discussions/1221


https://qiita.com/mm_sys/items/28a0217256b56918fee4
https://qiita.com/shunk_jr/items/3528340ed5c37259b9ae
https://qiita.com/akinami/items/d38b9e7c7f37bd070f40

