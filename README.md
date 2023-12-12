### 概要
- Ansible実行用Dockerコンテナ
- Ansibleをインストール

### インストール用URL
* Amazonlinux
https://hub.docker.com/_/amazonlinux/

* Ansible 2.9
https://docs.ansible.com/ansible/latest/roadmap/ROADMAP_2_9.html

### 利用手順
```
# ディレクトリ移動
cd docker-ansible

# 起動
docker-compose up -d

# docker接続
docker exec -it ansible.local bash
docker exec -it test01.local bash
docker exec -it test02.local bash

# 停止、削除
docker-compose down --rmi all --volumes --remove-orphans
```