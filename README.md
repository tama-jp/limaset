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
limactl stop default 
limactl delete default 
limactl start --debug --name=default debian12-arm.yaml 
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

```shell
❯ cat  ~/.lima/default/ssh.config
# This SSH config file can be passed to 'ssh -F'.
# This file is created by Lima, but not used by Lima itself currently.
# Modifications to this file will be lost on restarting the Lima instance.
Host lima-default
  IdentityFile "/Users/go/.lima/_config/user"
  StrictHostKeyChecking no
  UserKnownHostsFile /dev/null
  NoHostAuthenticationForLocalhost yes
  GSSAPIAuthentication no
  PreferredAuthentications publickey
  Compression no
  BatchMode yes
  IdentitiesOnly yes
  Ciphers "^aes128-gcm@openssh.com,aes256-gcm@openssh.com"
  User go
  ControlMaster auto
  ControlPath "/Users/go/.lima/default/ssh.sock"
  ControlPersist yes
  Hostname 127.0.0.1
  Port 60006
 
```

https://qiita.com/shunk_jr/items/3528340ed5c37259b9ae

- ホストにはHostの後ろに書いてあるlimaの環境名を入力します。 (Hostnameの方がうまく行く)
- ユーザー名にはUserの後ろに書いてあるユーザー名を入力します。
- 認証タイプはキーペアを選択します。
- 秘密鍵ファイルにはIdentityFileの後ろに書いてあるパスのうち、ファイル名がidで始まるものを入力します。
- パスフレーズは適当に入力します。（あとで使うので覚えといてください。）



https://dev.classmethod.jp/articles/lima-using-vm-on-macos-without-parallels-vmware/
https://github.com/lima-vm/lima/discussions/1890
ssh -F ./ssh-config lima-default

cat  ~/.lima/default/ssh.config

ssh -F ~/.lima/default/ssh.config lima-default

https://github.com/lima-vm/lima/discussions/1221


https://qiita.com/mm_sys/items/28a0217256b56918fee4
https://qiita.com/shunk_jr/items/3528340ed5c37259b9ae
https://qiita.com/akinami/items/d38b9e7c7f37bd070f40


## asdf

git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.0

vim ~/.bashrc

```shell
. "$HOME/.asdf/asdf.sh"
. "$HOME/.asdf/completions/asdf.bash"

```

// nodejs

```shell
apt-get install dirmngr gpg curl gawk
asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
asdf install nodejs latest
asdf global nodejs latest
asdf local nodejs latest
cat $HOME/.tool-versions
cat $PWD/.tool-versions


```

インストール済みプラグイン一覧

```shell
asdf plugin list
```

全プラグインのショートネーム一覧
```shell
asdf plugin list all

```

https://github.com/asdf-vm/asdf-plugins

go

```shell
asdf plugin add golang https://github.com/asdf-community/asdf-golang.git
asdf install golang latest

vim ~/.bashrc

. ~/.asdf/plugins/golang/set-env.bash

php

```shell
apt-get install mlocate
sudo apt install autoconf automake libtool gcc make


asdf plugin-add php https://github.com/asdf-community/asdf-php.git
```

asdf install php latest